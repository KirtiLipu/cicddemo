pipeline {
    agent none
	tools {
		maven 'my_maven'
	}
    stages {
        stage('CodeCollection') {
			agent any
            steps {
                git 'https://github.com/KirtiLipu/simple-java-maven-app.git'
            }
        }
		stage('Compilation'){
			agent {
				label 'Slave1'
			}
			steps {
				sh 'mvn clean'
				sh 'mvn compile'
			}
		}
		stage('Testing'){
			agent {
				label 'Slave2'
			}			
			steps {
				sh 'mvn test'
			}
		}
    }
}
