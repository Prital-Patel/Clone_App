# you-Tube clone App
A Modern YouTube Clone React Js Application deploy on EKS 

## Requirements
1. Jenkins
2. terraform
3. SonarQube
4. trivy
5. Docker Hub
6. EKS
7. Prometheus
8. Grafana

# Overview
The project involves deploying an application using Terraform to provision an EC2 instance and leveraging a CI/CD pipeline triggered by changes in a GitHub repository. The pipeline automates several stages including code analysis, dependency installation, security scanning, Docker image building and pushing to Docker Hub, Docker image scanning, and deployment to an EKS cluster. Monitoring of the Jenkins CI server and EKS cluster is done using Grafana and Prometheus.

# Flow:

## GitHub Repository Update:
Any changes pushed to the GitHub repository trigger the CI/CD pipeline.

## Jenkins Pipeline:
Triggered by changes in the repository.
Executes several stages in sequence.

## SonarQube Analysis:
Performs static code analysis using SonarQube to assess code quality, security vulnerabilities, and code smells.

## NPM Dependency Install:
Installs Node.js dependencies using npm to prepare for the build process.

## Trivy Filesystem Scan:
Conducts a security scan of the codebase using Trivy to detect any vulnerabilities in dependencies and libraries.

## Docker Image Build and Push:
Builds a Docker image containing the application code and its dependencies.
Pushes the built Docker image to Docker Hub, making it available for deployment.

## Trivy Docker Image Scan:
Scans the Docker image pushed to Docker Hub for any security vulnerabilities using Trivy.

## Deployment to EKS:
Deploys the Docker image onto an EKS cluster, ensuring that the application is running in a Kubernetes environment.

## Monitoring with Grafana and Prometheus:
Grafana and Prometheus are configured to monitor both the Jenkins CI server and the EKS cluster.
Metrics and dashboards are set up to provide insights into the health and performance of the CI/CD process and the deployed application.

