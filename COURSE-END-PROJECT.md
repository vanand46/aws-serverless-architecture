# Course-End Project: Deploying a Web Application to AWS

This project will guide you through the end-to-end process of deploying a containerized web application using modern cloud infrastructure.

### Project Workflow

1.  **Environment Preparation**
2.  **Build & Push Docker Image**
3.  **Deploy with ECS and Fargate**
4.  **Configure & Test**
5.  **Verify & Clean Up**

### Step 1: Prepare the Environment

**1.1 Go to the AWS console and create an EC2 instance of t2.micro**
    ![alt text](image.png)

**1.2 Run the command sudo apt update && sudo apt upgrade -y to update and upgrade the system packages**
    ![alt text](image-1.png)

**1.3 Run the command sudo apt install git -y to install the latest version of Git on your EC2 Ubuntu system** 
    ![alt text](image-2.png)

**1.4 Run the command sudo apt install docker.io -y to install Docker and its necessary dependencies**
    ![alt text](image-3.png)    

**1.5 Run the command sudo systemctl start docker to start the Docker service on your Ubuntu system, allowing you to run the Docker containers**    
    ![alt text](image-4.png)


### Step 2: Build and push the Docker image

**2.1 Run the command git clone https://github.com/ramkrishnatest/ECS-Fargate.git to download the ECS-Fargate project repository from GitHub to your local machine**
    ![alt text](image-5.png)

**2.2 Run the command cd ECS-Fargate/ to change your current directory to the ECS-Fargate directory**
    ![alt text](image-6.png)

**2.3 Run the command docker build -t deploy to create a Docker image named deploy from the Dockerfile in the current directory**
    ![alt text](image-7.png)
    ![alt text](image-8.png)

**2.4 Before configuring the AWS CLI, click on Security credentials, and then create the Access Key and Secret Key**
    ![alt text](image-9.png)
    ![alt text](image-10.png)

### Step 3: Deploy using ECS and Fargate

**3.1 Navigate to the Create Repository page on Amazon ECR, enter the repository name, and configure visibility settings to either Public or Private to create a new Docker image repository**
    ![alt text](image-11.png)
    ![alt text](image-12.png)

**3.2 Click on Repository and view Push commands; you will see the commands (as shown below) to push your Docker image to the ECR repository**    
    ![alt text](image-13.png)

    Go back to the EC2 console and tag the Docker image to push to the newly created ECR Registry using push commands displayed in the ECR dashboard

**3.3 Run the command sudo aws ecr-public get-login-password --region us-east-1 | sudo docker login --username AWS --password-stdin public.ecr.aws/b5d5d8u4 to authenticate your Docker client with AWS ECR as a superuser, enabling you to push and pull images**
    ![alt text](image-14.png)
    ![alt text](image-15.png)
    ![alt text](image-16.png)
 
 **3.4 Run the command sudo docker build -t webapp-image . to build a Docker image named webapp-image using the Dockerfile in the current directory with superuser permissions, ensuring all necessary Docker operations can execute without permission issues** 
    ![alt text](image-17.png)
    ![alt text](image-18.png) 

**3.5 Run the command docker push 531087812410.dkr.ecr.us-east-1.amazonaws.com/webapp-image:latest to upload the Docker image named simplilearn:latest to your AWS Elastic Container Registry using superuser privileges**
    ![alt text](image-19.png)

    Check and ensure that your image is successfully pushed to the ECR

    
    
