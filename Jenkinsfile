pipeline {
    agent any

    tools {
	maven 'apache-maven-3.9.4'
      
    }

    stages {
        stage('code clone') {
            steps {
			git credentialsId: 'git', url: 'https://github.com/suryavinay4435/new-jenkins.git'
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
			stage('code deploy') {
            steps {
			  sh 'mvn deploy'
                
            }
            }
         }
      }
