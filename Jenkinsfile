pipeline{

	agent any
	
	triggers {
        // poll repo every 2 minute for changes
        pollSCM('*/2 * * * *')
	}

	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/mach1el/docker-rtpproxy.git'
			}
		}

		stage('Build') {

			steps {
				sh 'docker build -t mich43l/rtpproxy:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push mich43l/rtpproxy:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}