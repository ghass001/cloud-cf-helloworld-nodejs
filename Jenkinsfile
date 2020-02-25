@Library('piper-lib-os') _
node() {
    stage('prepare') {
        sh 'git clone "https://ghass001:gh@$$En$oud@ni789456/github.com/SAP/cloud-cf-helloworld-nodejs.git"'
	sh 'git checkout 1_REST_persist_in_Memory'
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	echo 'building'
        sh 'mbt build --mtar com.sap.piper.node.hello.world.mtar --platform cf --target ./'
    }

    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}

