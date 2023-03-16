pipeline {
   
    agent any

    stages {

        stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
        }
        stage('Build') {
            steps {
                sh 'pwd'
                sh 'ls -la'
                sh 'npm install'
                sh 'npm build'
                sh 'ls -la'
            }

        }

        stage('Docker Image Build') {
            steps {
                sh 'docker build -t test-ecr .'
            }
        }

        stage('Push Docker Image to ECR') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'ap-south-1') {
                    sh 'aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/y0j0v8z3'
                    sh 'docker tag test-ecr:latest public.ecr.aws/y0j0v8z3/test-ecr:feature'
                    sh 'docker push public.ecr.aws/y0j0v8z3/test-ecr:feature'
                }
            }
        }
        
    }
}
