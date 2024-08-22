# ci-cd-pipeline-automation
A project to automate CI/CD pipeline for a simple web application.

### 1. **Project Title**
   - **CI/CD Pipeline Automation for Flask Application**

### 2. **Project Description**
   - This project demonstrates the setup and automation of a Continuous Integration/Continuous Deployment (CI/CD) pipeline using Jenkins, Docker, and Amazon Web Services (AWS). The pipeline is designed to build, test, and deploy a Flask-based Python application on AWS Elastic Container Service (ECS) with Fargate.

### 3. **Features**
   - Automated build and deployment using Jenkins.
   - Containerization of the Flask application with Docker.
   - Storage and versioning of Docker images in AWS Elastic Container Registry (ECR).
   - Deployment of the Docker container to AWS ECS with Fargate.
   - Continuous updates and redeployments triggered by changes to the codebase.

### 4. **Prerequisites**
   - **Software Requirements:**
     - Python 3.x
     - Docker
     - Jenkins
     - AWS CLI configured with necessary permissions
     - AWS account with ECS, ECR, and IAM configured

   - **AWS Resources:**
     - ECS Cluster and Service
     - ECR Repository
     - IAM roles and policies for ECS and Jenkins

### 5. **Setup Instructions**
   - **Clone the Repository:**
     ```bash
     git clone https://github.com/b-praveenkumar/ci-cd-pipeline-automation.git
     cd ci-cd-pipeline-automation
     ```
   - **Jenkins Setup:**
     - Install necessary Jenkins plugins (e.g., Docker Pipeline, AWS Pipeline).
     - Configure Jenkins credentials for AWS and GitHub.
     - Create a Jenkins pipeline job and point it to your Jenkinsfile in this repository.

   - **AWS Setup:**
     - Create an ECR repository to store Docker images.
     - Set up an ECS Cluster with a service configured to run the Flask application.

   - **Build and Deploy:**
     - Trigger a Jenkins build. Jenkins will:
       1. Build a Docker image for the Flask application.
       2. Push the Docker image to AWS ECR.
       3. Update the ECS service to deploy the new Docker image.

### 6. **Usage**
   - **Accessing the Application:**
     - Once deployed, you can access the application via the public IP assigned by AWS Fargate or through a Load Balancer if configured.

   - **Updating the Application:**
     - Push updates to the main branch of the repository. Jenkins will automatically rebuild, push, and redeploy the application.

### 7. **Troubleshooting**
   - **Common Issues:**
     - **Docker build errors:** Ensure that your Dockerfile is correctly configured.
     - **AWS ECS deployment issues:** Double-check your task definitions, security groups, and IAM permissions.

   - **Logs:**
     - Check the Jenkins console output for build and deployment logs.
     - Use AWS CloudWatch to view logs for the ECS service and troubleshoot any issues.

### 8. **Contributing**
   - Contributions are welcome! Please fork this repository and submit a pull request with your changes.

### 9. **License**
   - This project is licensed under the MIT License - see the LICENSE file for details.

### 10. **Acknowledgements**
   - Inspiration and guidance from various CI/CD and AWS tutorials and documentation.
