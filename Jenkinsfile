pipeline {
	agent any
	stages {
        stage('Build') {
             steps {
               	build job: 'Build'
				echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
			echo "${env.BUILD_ID} success"
        }
		}
        stage('Sonar') {
            steps {
				build job: 'report-generation'
				echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('HP Fortify') {
            steps {
				build job: 'perform code review'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
	stage('Deply') {
            steps {
				build job: 'deploy'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}" 
		}
	}   
}
}
}
