		pipeline {
    agent any
			tools {
				maven 'M2_HOME' 
				jdk 'JAVA_HOME' 
			}
    environment {
         GIT_CRED_ID = '35565503-41e8-4c64-88bb-66d301030a58'
        REPO_URL = 'git@github.com:tejprakashbkn/jenkins-example.git'
	    
    }
    stages {
        stage('Git Checkout') {
            steps {
                echo 'Checkout/Pull Code from Github'
                step([$class: 'WsCleanup'])
                checkout([
	                $class: 'GitSCM', 
	                branches: [[name: 'master']],  
	                userRemoteConfigs: [[credentialsId: GIT_CRED_ID, url: REPO_URL]]
	                ])
	           sh "ls -l"
                
            }
        }
        stage('Compile Code') {
            steps {
                echo 'using Maven Compile the code'
		sh '/usr/bin/mvn clean compile'    

            }
        }
        stage('Run Test Cases') {
            steps {
                echo 'Run Test Cases using Maven'
                sh 'mvn test'
            }
        }
        stage('Package the Code') {
            steps {
                echo 'Package code using Maven package command'
		sh 'mvn package'
            }
        }
    }
}
