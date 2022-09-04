pipeline {
    agent any 
    stages {
        stage('Cloning') {
            steps {
                git branch: 'main', credentialsId: '24c36649-faee-4cdd-abf2-9a6c3b27bb5f', url: 'https://github.com/aamizsameen/AWS.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t fastapi-image .'
            }
        }
        stage('Pushing to ECR') {
            steps{  
                script {
                    sh "aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 045996574415.dkr.ecr.us-east-1.amazonaws.com/apache-image:latest"
                    sh "docker build -t fastapi-image ."
                    sh "docker tag fastapi-image:latest 045996574415.dkr.ecr.us-east-1.amazonaws.com/apache-image:latest"
                    sh "docker push 045996574415.dkr.ecr.us-east-1.amazonaws.com/apache-image:latest"
                }
            }
        }
        
    }
}


