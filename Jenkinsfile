pipeline {
    agent any
    environment {
        ECR_REPO = "054031713023.dkr.ecr.us-east-1.amazonaws.com/akshay_app:v1"
    }
    stages {
        stage('Akshay - Build Docker Image') {
            steps {
                sh 'docker build -t $ECR_REPO .'
            }
        }
        stage('Akshay - Login to ECR') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 054031713023.dkr.ecr.us-east-1.amazonaws.com'
            }
        }
        stage('Akshay - Push Image to ECR') {
            steps {
                sh 'docker push $ECR_REPO'
            }
        }
    }
}
