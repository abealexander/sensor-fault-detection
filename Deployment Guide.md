1. Login to AWS console.

2. Create IAM user for deployment

	With specific access
	1. EC2 access : It is virtual machine
	2. S3 bucket: To store artifact and model in s3 bucket
	3. ECR (Elastic Container Registry): To save your docker image in aws
	
	Description: About the deployment

	1. Build docker image of the source code
	2. Push your docker image to ECR
	3. Launch Your EC2 
	4. Pull Your image from ECR in EC2
	5. Launch your docker image in EC2

	Policy:
	1. AmazonEC2ContainerRegistryFullAccess
	2. AmazonEC2FullAccess
	3. AmazonS3FullAccess

3. Create a S3 bukcet in ap-south-1
	
4. Create an ECR repo to store/save docker image
	
5. Create an EC2 machine with Ubuntu OS

6. Open EC2 and install docker in EC2 Machine by running the following commands
	
	#optional
	sudo apt-get update -y
	sudo apt-get upgrade
	
	#required
	curl -fsSL https://get.docker.com -o get-docker.sh
	sudo sh get-docker.sh
	sudo usermod -aG docker ubuntu
	newgrp docker
	
7. Configure EC2 as self-hosted runner

	Setting>Actions>Runner>New Self Hosted Runner> Choose OS>Linux 
	Run the provided commands in your EC2 command line

8. Setup github secrets

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_REGION
* AWS_ECR_LOGIN_URI
* ECR_REPOSITORY_NAME
* MONGO_DB_URL