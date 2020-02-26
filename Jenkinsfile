@Library('piper-lib-os') _
def scr
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	src = load 'mtaBuild.groovy'
        src.exec(this)
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}



