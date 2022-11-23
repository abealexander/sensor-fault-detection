# Sensor-Fault-Detection
### Problem Statement
The Air Pressure System (APS) is a critical component of a heavy-duty vehicle that uses compressed air to force a piston to provide pressure to the brake pads, slowing the vehicle down. The benefits of using an APS instead of a hydraulic system are the easy availability and long-term sustainability of natural air.

This is a Binary Classification problem, in which the affirmative class indicates that the failure was caused by a certain component of the APS, while the negative class indicates that the failure was caused by something else.

### Solution Proposed 
In this project, the system in focus is the Air Pressure system (APS) which generates pressurized air that are utilized in various functions in a truck, such as braking and gear changes. The datasets positive class corresponds to component failures for a specific component of the APS system. The negative class corresponds to trucks with failures for components not related to the APS system.

The problem is to reduce the cost due to unnecessary repairs. So it is required to minimize the false predictions.

## Tech Stack Used
1. Python 
2. FastAPI 
3. Machine learning algorithms
4. Docker
5. MongoDB

## Infrastructure Required.

1. AWS S3
2. AWS EC2
3. AWS ECR
4. Git Actions
5. Terraform

## How to run?
Before we run the project, make sure that you are having MongoDB in your local system, with Compass since we are using MongoDB for data storage. You also need AWS account to access the service like S3, ECR and EC2 instances.

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
	5. Lauch your docker image in EC2

	Policy:
	1. AmazonEC2ContainerRegistryFullAccess
	2. AmazonEC2FullAccess
	3. AmazonS3FullAccess

3. Create a s3 bukcet in ap-south-1
	
4. ECR repo to store/save docker image
	
5. EC2 machine  Ubuntu  Created

6. Open EC2 and Install docker in EC2 Machine by running the following commands
	
	#optional
	sudo apt-get update -y
	sudo apt-get upgrade
	
	#required
	curl -fsSL https://get.docker.com -o get-docker.sh
	sudo sh get-docker.sh
	sudo usermod -aG docker ubuntu
	newgrp docker
	
7. Configure EC2 as self-hosted runner

Setting>Actions>Runner>New Self Hosted Runner> Choose OS> Linux 
Run the provided commands in your EC2 command line

8. Setup github secrets

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_REGION
* AWS_ECR_LOGIN_URI
* ECR_REPOSITORY_NAME
* MONGO_DB_URL

## Data Collections
![image](https://user-images.githubusercontent.com/57321948/193536736-5ccff349-d1fb-486e-b920-02ad7974d089.png)


## Project Architecture
![image](https://user-images.githubusercontent.com/57321948/193536768-ae704adc-32d9-4c6c-b234-79c152f756c5.png)


## Deployment Architecture
![image](https://user-images.githubusercontent.com/57321948/193536973-4530fe7d-5509-4609-bfd2-cd702fc82423.png)