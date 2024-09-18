pipeline {
    agent any

    tools {
	maven 'Apache Maven 3.0.5'
      
    }

    stages {
        stage('code clone') {
            steps {
			git branch: 'main', credentialsId: 'git', url: 'https://github.com/suryavinay4435/new-jenkins.git'
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
			stage('sonar scan') {
            steps { 
            sh 'mvn sonar:sonar -Dsonar.host.url=http://13.201.59.55:9000 -Dsonar.login=a4df5dede22c1f8c9573d2789ca3b5e53f21c280'			
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
			stage('code deploy') {
            steps {
			  sh 'mvn deploy'
                
            }
            }
         }
      }
