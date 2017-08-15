pipeline {
    agent any
	checkout([$class: 'GitSCM', branches: [[name: '*/continuous-delivery-demo']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/karavindcc/game-of-life.git']]])

    stages {
        stage('Build') {
            steps {
                build job: 'Build'
		echo 'Building..'
		junit '**/target/*.xml'
            }
        }
        stage('Sonar') {
            steps {
		build job: 'report-generation'
                echo 'Sonar reports..'
            }
        }
        stage('HP Fortify') {
            steps {
		build job: 'perform code review'
                echo 'Fortify reports..'
            }
        }
	stage('Deply') {
            steps {
		build job: 'deploy'
                echo 'Deploying..' 
		}
	}   
}
