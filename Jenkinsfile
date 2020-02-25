@Library('piper-lib-os') _
pipeline {
    agent none 
    stages {
        stage('prepare') { 
            steps {
                echo 'prepare'
                setupCommonPipelineEnvironment script:this
            }
        }
    }
}


