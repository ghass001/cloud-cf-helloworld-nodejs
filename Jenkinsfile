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

    stage('bld') {
        scr script: this
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}



