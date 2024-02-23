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
            sh 'mvn sonar:sonar -Dsonar.projectKey=webproject -Dsonar.host.url=http://13.232.101.61:9000 -Dsonar.login=4706196c3b563c7db98f41717d6f82a937cbb44d'			
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