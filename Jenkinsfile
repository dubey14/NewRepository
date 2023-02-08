pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker-hub')
	}

	stages {

		stage('Build') {
			steps {
			echo 'hello ali'
			echo 'docker build -t tanayvan/nodeapp:latest .'
			}
		}

		stage('Login') {

			steps {
				echo 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				echo 'docker push tanayvan/nodeapp:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}