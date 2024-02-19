pipeline {
    agent any

    tools {
	maven 'apache-maven-3.9.4'
      
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
			sh 'mvn sonar:sonar -Dsonar.projectKey=New -Dsonar.host.url=http://15.207.115.106:9000 -Dsonar.login=dfa8c5b3fa12d7fbfce59f0066c47b4d563aa497'   
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
