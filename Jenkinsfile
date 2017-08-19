pipeline {
	agent any
	stages {
        stage('Build') {
             steps {
               	build job: 'Build'
		script {
                    def bRun = build 'anotherJob' 
                    echo 'last 100 lines of BuildB'
                    for(String line : bRun.getRawBuild().getLog(100)){
                        echo line
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
