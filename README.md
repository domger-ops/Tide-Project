### CI/CD Automation for an Application

This repository is a main hub to explain this project, and the skills it demonstrates.

### Brief Overview:
Workflow that automates and ensures the consistency of application deployment on a GKE cluster by automatically updating and running the latest Docker image for a CronJob whenever the application code is updated and pushed to GitHub, integrating seamlessly with CI/CD pipelines and reducing operational overhead and errors.

### Solution Outline:
GKE Cluster Setup: The GKE cluster is created using Terraform.

Application Deployment: The application, which performs multiple API calls and delivers values to be monitored, runs as a Kubernetes CronJob on the GKE cluster.

Source Code Management: The application's source code is hosted on GitHub.

Docker Image Creation: Each time the application is updated and pushed to GitHub, a new Docker image is created and pushed to Docker Hub.

CronJob Update: The Argo CD manifest repository, which contains the Kubernetes CronJob definition, is updated with the new Docker image tag. This ensures that the CronJob is always running the intended version of the application.

Continuous Deployment: Argo CD monitors the Git repository for changes to the manifest and deploys the updated CronJob to the GKE cluster.

This workflow ensures that every update to the application is automatically reflected in the CronJob running on the GKE cluster, maintaining consistency and enabling continuous deployment.

### Repositories:
In order to keep the project organized, it is broken down into 3 github repositories. Please see each repository's detailed ReadMe for more information:
- (tide-app-workflow) https://github.com/domger-ops/tide-app-workflow.git - To manage the application and CI
- (tide-gke-resources) https://github.com/domger-ops/tide-gke-resources - To manage the infrastructure that the application is running on 
- (tide-argo-manifest) https://github.com/domger-ops/tide-argo-manifest - To manage the CD manifest 






