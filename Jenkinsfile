pipeline {
	agent {
	    label 'node1'
	}
	 tools {
        // Using the JDK and Maven tools configured in Global Tool Configuration
        //jdk 'JDK 11'  // Name of the JDK configuration
        maven 'mvn'  // Name of the Maven configuration
        }
 	//environment {
        // Define any environment variables if needed, for example, Maven or Java paths
        //MAVEN_HOME = 'C:\\Program Files\\apache-maven-3.9.9'  // Path to Maven installation
        //JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'  // Path to JDK installation
        //}
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
				sh "mvn clean package -DskipTests -Djacoco.skip=true"
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
