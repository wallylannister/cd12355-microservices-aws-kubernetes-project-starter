# 1. Build and Deploy Containers to ECR
Purpose:
To store Docker images in a secure and scalable container registry provided by AWS.

Steps:
### Build Docker Image: Create a Docker image of the analytics application.
### Push to ECR: Push this Docker image to Amazon Elastic Container Registry (ECR).
=> Storing Docker images in ECR allows engineers to manage container images in a centralized repository, making it easier to deploy them to various environments.

# 2. Run CodeBuild Pipeline to Deploy Docker Image to AWS ECR
Purpose:
To automate the process of building and pushing Docker images to ECR using AWS CodeBuild.

Steps:
### Configure AWS CodeBuild: Set up a build project that triggers automatically.
### Build and Push: The pipeline builds the Docker image and pushes it to ECR.
=> Automation ensures consistency and efficiency. Every time engineers push code changes, the pipeline will automatically build and deploy the updated Docker image.

# 3. Kubernetes Configuration
Purpose:
To deploy application using Kubernetes, which manages containerized applications across a cluster of machines.

Steps:
### Create Deployment Configs: Write Kubernetes YAML files to define how the application should be deployed.
### Create Service Configs: Define how the application should be exposed and accessed.
### ConfigMaps and Secrets: Manage environment variables and sensitive data.
=> Kubernetes provides powerful orchestration capabilities, ensuring that application is scalable, resilient, and easy to manage.

# 4. Successfully Deploy Kubernetes Service
Purpose:
To verify that Kubernetes deployment is working correctly.

Steps:
### Deploy Application: Use kubectl commands to deploy analytics application.
### Verify Deployment: Check the status of the services and pods to ensure they are running correctly.
=> Verification ensures that the application is correctly deployed and running as expected in the Kubernetes cluster.

# 5. Create a Kubernetes Database Service
Purpose:
To deploy a database service (e.g., PostgreSQL) within Kubernetes cluster.

Steps:
### Write YAML Config: Create a Kubernetes service configuration for the database.
### Deploy and Verify: Deploy the database service and verify its status.
=> Managing database within the same Kubernetes cluster ensures better integration, scalability, and management.

# 6. Logging and Documentation
Purpose:
To provide clear documentation and ensure application logs are accessible for monitoring and troubleshooting.

Steps:
### Write README: Create a concise and well-structured README file.
### CloudWatch Logs: Set up logging to AWS CloudWatch to monitor the health and performance of the application.
=> Good documentation helps others understand the project, and logging is crucial for maintaining and troubleshooting the application

# Stand-Out Suggestions

Specify reasonable Memory and CPU allocation in the Kubernetes deployment configuration
## => Based on metrics from ContainerInsights, CPU & Memory Utilization of t3.large running instance are 3% and 10%, which are below average. So, the reasonable for CPU & Memory could be as low as 1 vCPU and 2 GiB
In your README, specify what AWS instance type would be best used for the application? Why?
## => From the previous conclusion, the recommened AWS instance type is t2.small to help us save cost from unused resources
In your README, provide your thoughts on how we can save on costs?
## => Leverage The Horizontal Pod Autoscaler to allow a deployment to scale up and down horizontally to address load. This way, we can save the cost from over-provisioning, help our application remain elastic and not fail over from traffic
