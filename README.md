# DevOps Engineer Task - Deploy `echo-server` to Kubernetes

## Task Overview
You are required to deploy the [`ealen/echo-server`](https://hub.docker.com/r/ealen/echo-server) container to a Kubernetes cluster using **Helm** and **Terraform's Helm provider**. The task involves containerizing the application with a minor modification, creating a Helm chart, deploying it using Terraform, and setting up a CI/CD pipeline for automated deployments.

This task is expected to take **60 minutes** and will be conducted via screen sharing.

---

## **Task Breakdown**

### **1. Fork & Modify the Docker Image**
- Complete the `Dockerfile` with a minor change:
  - Update the `global.json` configuration to change the `port` from **80** to **8080**.
- Build and push the modified image to **Docker Hub** or **GitHub Container Registry (GHCR)**.

### **2. Create a Helm Chart**
- Write a Helm chart to deploy `ealen/echo-server`.
- Include a `values.yaml` file for configuration (e.g., setting environment variables, replica count, service type, etc.).
- Ensure the Helm chart is reusable and configurable.

### **3. Deploy Using Terraform**
- Use **Terraform's Helm provider** to deploy the Helm chart to a Kubernetes cluster.
- Parameterize the deployment (e.g., image tag, number of replicas, namespace).
- Output the service URL after deployment.

### **4. Setup a Git Repository Structure**
- Organize your repository with the following structure:

```
repo-root/
│── helm/
│   ├── Chart.yaml
│   ├── values.yaml
│   ├── templates/
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│── .github/
│   ├── workflows/
│   │   ├── ci-cd.yaml
│── Dockerfile
│── README.md
```

### **5. CI/CD Pipeline with GitHub Actions**
- Create a GitHub Actions pipeline (`.github/workflows/ci-cd.yaml`) that:
  - Builds the Docker image and pushes it to a registry when a **feature branch** is merged to `main`.
  - Deploys to **staging** when changes are merged into `main`.
  - Deploys to **production** when a release is published.

---

## **Deliverables**
- A GitHub repository containing:
  - Helm chart (`helm/` directory)
  - Terraform files (`terraform/` directory)
  - A GitHub Actions pipeline (`.github/workflows/ci-cd.yaml`)
  - A modified Dockerfile
  - A structured `README.md`

## **Bonus (if time permits)**
  - ArgoCD application manifest (argo-cd/applications/echo-server.yaml)


## **Evaluation Criteria**
- **Code quality & organization**: Clean and structured repository.
- **AI Usage**: Usage of AI tools is allowed, and actually encouraged.
- **git commit messages**: Commit messages should be concise and descriptive.
- **Infrastructure as Code (IaC)**: Proper use of Terraform & Helm.
- **CI/CD implementation**: A working pipeline that follows best practices.
- **Completeness**: Successful deployment of `ealen/echo-server`.