node('linuxslave') {
   echo ' Will run on the slave with name or tag specialSlave'
    stage('Setting BUILDSCRIPTS_DIR'){
        env.BUILDSCRIPTS_DIR = "${WORKSPACE}/${BUILDSCRIPTS_DIR}"
    }

     /*stage('Latest Changes'){
        passedBuilds = []

        lastSuccessfulBuild(passedBuilds, currentBuild);

        for(int i=0; i<passedBuilds.size();i++){
            print(passedBuilds[i].getNumber());
        }

        def changeLog = getChangeLog(passedBuilds)
        echo "changeLog is  ${changeLog}"
    }*/

    stage('Multiple SCM checkout ') {
        echo 'SCM checkout..'
        checkout([$class: 'GitSCM', branches: [[name: '${BUILDSCRIPTS_REPO_BRANCH}']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: '${BUILDSCRIPTS_DIR}']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitHubCredentials', url: '${BUILDSCRIPTS_REPO_URL}']]])
    }
}

