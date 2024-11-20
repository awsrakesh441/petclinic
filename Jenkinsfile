pipeline {
	agent any
	environment {
        // Define any environment variables if needed, for example, Maven or Java paths
        MAVEN_HOME = 'C:\\Program Files\\apache-maven-3.9.9'  // Path to Maven installation
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'  // Path to JDK installation
        }
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
				bat 'mvn clean package'
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
