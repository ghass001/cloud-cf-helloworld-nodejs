@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
	echo 'scm'
        sh 'pwd'
	sh 'ls'
	sh 'git checkout 1_REST_persist_in_Memory'
	echo 'checkout'
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	echo 'building'
	sh 'pwd'
        sh 'mbt build -s /var/lib/jenkins/workspace/ipeline_1_REST_persist_in_Memory/cloud-cf-helloworld-nodejs --mtar com.sap.piper.node.hello.world.mtar --platform cf --target ./'
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}

