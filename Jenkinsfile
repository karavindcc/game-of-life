pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Sonar') {
            steps {
                echo 'Sonar reports..'
            }
        }
        stage('HP Fortify') {
            steps {
                echo 'Fortify reports..'
            }
        }
	stage('Deply') {
            steps {
                echo 'Deploying..' 
		}
	}   
}
