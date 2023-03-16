# SampleExpressApp

Used for Devops interview

STEP BY STEP CICD 


Launch a virtual machine of any linux flavour and install jenkins, docker, AWS CLI and nodejs

Create a registry in AWS ECR and create IAM user with required permission to carry out ECR activities.

Create EKS cluster using AWS CLI along with creation of IAM role with cloudformation, IAM &  EC2 permissions.

Create AWS access key and secret keys from IAM user

Access jenkins through port 8080 on browser and download AWS:Pipeline, ECR, docker pipeline, EKS, cloudbees plugins

Store AWS credentials in jenkins which are required to login to ECR

Create Dockerfile (As shown in repo) and Jenkinsfile with necessary steps and stages

Create K8S manifest file for Deployment and services and choose type as Nodeport (With appropriate port of an application)

Now, access this application with Node IP:NodePort on browser.
