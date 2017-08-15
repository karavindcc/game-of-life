pipeline {
	agent any
       stages {
        stage('Build') {
            steps {
                build job: 'Build'
		echo 'Building..'
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
}
