pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
         jdk 'JDK'  
     }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: ''
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }
        
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
