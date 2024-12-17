***Python Game on AWS EKS***

This repository hosts a Python game application deployed on an AWS Elastic Kubernetes Service (EKS) cluster.
Below is an overview of the architecture and deployment workflow.

**Application Overview**
- Game Access: Only authenticated users with valid credentials can play the game.
- Database: The application uses PostgreSQL as its database backend.

**Architecture and Features**

**1. AWS EKS Cluster:**
- The Kubernetes cluster is configured to autoscale based on node CPU utilization.
- Access to the cluster is secured via a bastion host.

**2. CI/CD Pipeline:**
- A Jenkins server orchestrates the CI/CD pipeline.
- Pipeline Workflow:
    - Code is stored in Git.
    - On every git push, the pipeline is triggered.
    - Jenkins checks the code, builds the application, pushes the Docker image to Docker Hub, and updates the Kubernetes deployment.
    - The cluster pulls the latest image from Docker Hub to ensure the deployment is up-to-date.

**3. Cost Optimization:**
The infrastructure is automatically shut down twice daily to reduce operational costs.

**4. Monitoring:**
Cluster performance is continuously monitored using Datadog.

**5. Load Balancer:**
The application is exposed to users via a Kubernetes Load Balancer.



**For developers:**
(Soon to come, full instructions on how to initialize this)
