@Library('piper-lib-os') _
def scr
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    
    stage('load') {
        scr = load 'mtaBuild.groovy'
    }

    stage('build') {
        mtaBuild script: scr
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}



