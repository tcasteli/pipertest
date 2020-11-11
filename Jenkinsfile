@Library('piper-lib-os') _
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

_@Library('piper-lib-os') _
pipeline {
    agent { label 'SCP Fiori Build Agent' } 
    tools { nodejs 'NodeJS' } 
    stages{ 
        stage('prepare'){ 
            steps { 
                deleteDir() 
                checkout scm 
                setupCommonPipelineEnvironment(script: this) } } }