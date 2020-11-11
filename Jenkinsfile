@Library('piper-lib-os@v1.34.0') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script: this
    }
    stage('build') {
        mtaBuild script: this, buildTool: 'mta'
    }
    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}