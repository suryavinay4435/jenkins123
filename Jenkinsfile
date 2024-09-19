pipeline {
    agent any

    tools {
	maven 'apache-maven-3.9.9'
      
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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://3.6.92.124:9000 -Dsonar.login=88080a42e1cefe3eb289103d6487a895cd03a7c5'			
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
