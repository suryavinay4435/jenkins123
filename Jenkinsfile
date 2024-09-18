pipeline {
    agent any

    tools {
	maven 'apache-maven-3.8.8'
      
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
            sh 'mvn sonar:sonar -Dsonar.projectKey=demoproject -Dsonar.host.url=http://13.201.59.55:9000 -Dsonar.login=6dc899be52a8223d42ddc6c4d6ec58e4baac2d71'			
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
