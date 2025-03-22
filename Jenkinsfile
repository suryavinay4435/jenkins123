pipeline {
    agent any
	
    environment {
        MAVEN_OPTS = "--add-opens java.base/java.lang=ALL-UNNAMED"
    }

    tools {
        maven 'maven 3.9.9'
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
                sh 'mvn sonar:sonar -Dsonar.host.url=http://65.0.100.234:9000 -Dsonar.login=6a7ebf4d06d9b57c7cd4bd0759ea014875e12e2d'			
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
                script {
                    // Deploying with a custom settings.xml file
                    def status = sh(script: 'mvn -s /home/ec2-user/apache-maven-3.9.9/conf/settings.xml deploy', returnStatus: true)
                    if (status != 0) {
                        error "Deployment failed!"
                    }
                }
            }
        }
    }
}
