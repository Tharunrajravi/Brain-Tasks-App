# Brain Tasks App – End-to-End DevOps Pipeline using Docker, AWS, and Kubernetes

Project Overview

This project demonstrates deploying a containerized application using AWS DevOps services and Kubernetes. The workflow includes building a Docker image, storing it in Amazon ECR, automating the build using CodeBuild, creating a CI/CD pipeline using CodePipeline, deploying the application to an Amazon EKS cluster, and monitoring the system using CloudWatch.

## Technologies Used

- AWS EC2
- Amazon ECR
- Amazon EKS
- AWS CodeBuild
- AWS CodePipeline
- AWS CloudWatch
- Docker
- Kubernetes
- GitHub

Project steps:

1. Connected to EC2 Instance

 Launched an EC2 instance to perform the DevOps setup.

 Connected to the instance using SSH.

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 11-51-13" src="https://github.com/user-attachments/assets/c36ac338-8489-42d7-bb7f-e318c236b331" />


2. Cloned the Provided Repository

Cloned the provided GitHub repository to the EC2 instance.

Navigated into the project directory.

Created a Docker image for the application using the Dockerfile.

Built the Docker image using Docker.

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 11-53-05" src="https://github.com/user-attachments/assets/1b63394a-df0d-4c76-96be-dc27c7d98557" />


3. Tagged and Pushed Docker Image to Amazon ECR

Created an Amazon ECR repository.

Logged in to Amazon ECR.

Tagged the Docker image with the ECR repository URI.

Pushed the Docker image to Amazon ECR.

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 11-31-29" src="https://github.com/user-attachments/assets/26dbe780-2d58-4678-8b0c-b29305be85e6" />

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 11-31-38" src="https://github.com/user-attachments/assets/c214989b-91f4-40a2-8068-43bd8cc97fb1" />


4. Created Amazon EKS Cluster

Created an Amazon EKS cluster using eksctl.

AWS automatically created the required VPC, subnets, and worker nodes.

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 11-53-48" src="https://github.com/user-attachments/assets/90f510f7-4469-4ddf-bc2b-f65cc9a581b1" />


<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-27-25" src="https://github.com/user-attachments/assets/ca08d9ba-8abc-4083-a1de-6abe2daeee97" />


<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-27-48" src="https://github.com/user-attachments/assets/348cd279-08b6-4440-9a45-627d299609a4" />

5. Created a buildspec.yml file

Added build instructions required for the CodeBuild process.

Defined steps for building the Docker image and pushing it to ECR.


6. Configured AWS CodeBuild

Created a CodeBuild project.

Connected it with the GitHub repository.

Configured it to use the buildspec.yml file.

# CodeBuild Successful Execution

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 15-44-54" src="https://github.com/user-attachments/assets/8a16e25b-6a3b-4565-a2f4-54e16888486a" />

7. Created AWS CodePipeline

Created a CI/CD pipeline using AWS CodePipeline.

Configured GitHub as the source stage.

Connected CodeBuild as the build stage.

Pipeline automatically triggers when code changes are pushed.

# CodePipeline Execution

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-02-41" src="https://github.com/user-attachments/assets/4d9033db-f5f9-4d48-aba6-a1d16d29222a" />

8. Verified running pods and services

Verified that the pods were running successfully.

Confirmed that the service was created with type LoadBalancer.

Kubernetes Pods and Services

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-16-41" src="https://github.com/user-attachments/assets/b780bc6d-66be-4893-90d7-5631ea267dfb" />

9. Accessed the application through LoadBalancer

AWS automatically created an Elastic Load Balancer.

Accessed the application through the LoadBalancer DNS endpoint.

Application deployed kubernetes Loadbalancer ARN: arn:aws:elasticloadbalancing:ap-south-1:919468641180:loadbalancer/net/a03cc36a5750b491baebe7575dd0e8c4

# Application Running in Browser

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 12-14-45" src="https://github.com/user-attachments/assets/ffe85de2-f308-429d-b69f-d57ed3151860" />

10. Monitored metrics using Amazon CloudWatch

Used CloudWatch to monitor system metrics and build execution.

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-24-37" src="https://github.com/user-attachments/assets/7992d83a-adf1-438c-b995-74f5dfa2c76f" />

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-26-03" src="https://github.com/user-attachments/assets/6d59ce9c-a89b-4b71-be2d-e1580a7ba188" />

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-26-15" src="https://github.com/user-attachments/assets/0ff88d74-fcbc-46e4-9231-2056fa7451f9" />

<img width="1855" height="1079" alt="Screenshot from 2026-03-11 16-26-50" src="https://github.com/user-attachments/assets/eb0c3a68-8ef1-4c39-a197-35c443fa9253" />


