pipeline {
    agent any

    tools {
	maven 'maven'
      
    }

    stages {
        stage('code clone') {
            steps {
			git credentialsId: 'github', url: 'https://github.com/kartikeyapro/ks.git'
                
            }
            }
			stage('code clean') {
            steps {
			sh 'mvn clean'
                
            }
            }
			stage('code validate') {
            steps {
			sh 'mvn validate'
                
            }
            }
			stage('code compile') {
            steps {
			sh 'mvn compile'
                
            }
            }
			stage('code test') {
            steps {
			sh 'mvn test'
                
            }
            }
			stage('code package') {
            steps {
			sh 'mvn package'
                
            }
            }
         }
      }