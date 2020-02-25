@Library('piper-lib-os') _
pipeline {
    agent none 
    stages {
        stage('prepare') { 
            steps {
                echo 'prepare'
		node() {
		     stage("scm") {
	                checkout scm
                        setupCommonPipelineEnvironment script:this
                     }
		}
            }
        }
    }
}


