# 🏦 ABC Bank - Static Website Deployment using Jenkins & Docker

## 📖 Project Overview

This project demonstrates a complete DevOps CI/CD workflow by deploying a static banking website using **GitHub**, **Jenkins**, **Docker**, **Docker Hub**, and a **Google Cloud Platform (GCP) Virtual Machine**.

The website is built using **HTML, CSS, and Bootstrap** and is deployed automatically through a Jenkins pipeline.

---

# 🚀 Project Objective

The objective of this project is to understand how a DevOps Engineer automates the deployment of a web application using Jenkins and Docker.

---

# 🛠 Technologies Used

- HTML5
- CSS3
- Bootstrap 5
- Git
- GitHub
- Jenkins
- Docker
- Docker Hub
- Google Cloud Platform (GCP)
- Ubuntu Linux

---

# 📂 Project Structure

```
Bank-Demo/
│
├── index.html
├── Dockerfile
├── Jenkinsfile
└── README.md
```

---

# 🌐 Website Features

The website contains:

- Responsive Navigation Bar
- Hero Banner
- Banking Services Section
- Credit Card Information
- Home Loan Information
- Mobile Banking Information
- Bootstrap Responsive Design

---

# 🐳 Docker Workflow

## Build Docker Image

```bash
docker build -t sushmamounika/bank-app:v1 .
```

---

## Push Image to Docker Hub

```bash
docker push sushmamounika/bank-app:v1
```

---

## Pull Image

```bash
docker pull sushmamounika/bank-app:v1
```

---

## Run Docker Container

```bash
docker run -d \
--name bank-app \
-p 80:80 \
sushmamounika/bank-app:v1
```

---

# ⚙ Jenkins Pipeline Stages

The Jenkins pipeline performs the following tasks:

### Stage 1 - Clone Repository

Downloads the latest source code from GitHub.

---

### Stage 2 - Verify Files

Checks whether all required files are available.

Commands used:

```bash
pwd
ls -la
find . -maxdepth 2
```

---

### Stage 3 - Build Docker Image

Builds the Docker image using the Dockerfile.

---

### Stage 4 - Push Docker Image

Uploads the Docker image to Docker Hub.

---

### Stage 5 - Pull Latest Image

Pulls the latest Docker image from Docker Hub.

---

### Stage 6 - Deploy Container

Stops the old container (if running) and deploys the latest version.

---

# 🔄 CI/CD Workflow

```
Developer

      │

      ▼

GitHub Repository

      │

      ▼

Jenkins Pipeline

      │

      ├── Clone Repository

      ├── Verify Files

      ├── Build Docker Image

      ├── Push Docker Image

      ├── Pull Latest Image

      ├── Deploy Docker Container

      ▼

Docker Container

      ▼

ABC Bank Website
```

---

# 📸 Application Access

Once the pipeline completes successfully, the application can be accessed using the GCP VM External IP.

Example:

```
http://34.xxx.xxx.xxx
```

---

# 📚 What I Learned

This project helped me understand:

- GitHub Integration with Jenkins
- Jenkins Declarative Pipelines
- Docker Image Creation
- Docker Hub Image Management
- Docker Container Deployment
- CI/CD Pipeline Automation
- Application Hosting on GCP VM
- Troubleshooting Jenkins Build Issues
- Docker Volume Management
- Container Lifecycle Management

---

# 🔧 Challenges Faced

During the implementation, the following issues were encountered and resolved:

- Jenkins Built-in Node went Offline due to low disk space.
- Docker storage consumed the boot disk.
- Mounted a dedicated 30 GB disk for Jenkins Docker volume.
- Fixed Jenkins Pipeline syntax errors.
- Fixed missing Git Clone stage.
- Fixed Dockerfile not found issue.
- Successfully deployed the website after pipeline corrections.

---

# 🎯 Future Enhancements

- Add GitHub Webhooks for automatic builds.
- Add HTTPS support using Nginx.
- Deploy on Kubernetes (GKE).
- Add Monitoring using Prometheus and Grafana.
- Integrate SonarQube for code quality.
- Integrate Trivy for Docker image security scanning.

---

# 👨‍💻 Author

**Sushma Mounika**

DevOps Engineer

---

# ✅ Project Status

**Completed Successfully**

✔ Static Website Developed

✔ Dockerized Application

✔ Jenkins CI/CD Pipeline Created

✔ Docker Hub Integration
----------------------------
<img width="1919" height="1096" alt="image" src="https://github.com/user-attachments/assets/01172593-f53c-4d41-a361-9f9abfffe26b" />
<img width="1911" height="1142" alt="image" src="https://github.com/user-attachments/assets/66cfbd50-73e7-447d-8834-7700a3ff3bc1" />
<img width="1919" height="1164" alt="image" src="https://github.com/user-attachments/assets/03cde021-fdf3-4e43-a47a-87985e2d98b7" />



✔ Container Deployment

✔ Website Accessible through GCP VM Public IP
