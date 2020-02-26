@Library('piper-lib-os') _
def scr
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	scr = load 'mtaBuild.groovy'
	scr.mtaBuild(this) script: this
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}



