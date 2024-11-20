pipeline {
	agent any
	stages {
		stage('checkout') {
			steps {
		             // start with  clean workspce
			     deleteDir()
		             //checkout branch
		             checkout scm
			}
		}
		stage('build') {
			steps {
				mvn clean package
		                // sh "docker build . -t  ${ENV}"
			}
		}
		stage('Docker build image && push') {
			steps {
				echo "build"
				//sh "docker login -u bskreddy18 -p ${DOCKER_HUB}"
				//sh "docker push ${ENV}:latest"
			}
		}
		stage('deploy to kuberneters') {
			steps {
				echo "need to setup"
			}
		}
    }
}
