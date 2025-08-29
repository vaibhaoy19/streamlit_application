# 🚀 Deployment of Python-Based Streamlit Application using Docker on AWS EC2

A DevOps project demonstrating how to containerize and deploy a **Python Streamlit web application** using **Docker** on an **AWS EC2 instance**, and publish the Docker image to **DockerHub** for global access.  

---

## 📌 Objective
To containerize and deploy a Python-based Streamlit web application on AWS EC2 using Docker. The project showcases:
- Cloud deployment  
- Containerization  
- Version control with Git/GitHub  
- Image publishing via DockerHub  
- Modern DevOps practices  

---

## 📖 Introduction
This project blends **DevOps**, **Docker**, and **Cloud Deployment** principles.  
- Docker ensures **consistent & portable deployment**.  
- AWS EC2 provides a **scalable environment**.  
- DockerHub is used for **remote image storage & reusability**.  

---

## 🛠️ Tools & Technology Used
| Tool / Service   | Purpose |
|------------------|---------|
| **Python 3.10**  | Application backend logic |
| **Streamlit**    | Web UI framework |
| **Docker**       | Containerization |
| **AWS EC2**      | Cloud deployment server |
| **Git & GitHub** | Source control & versioning |
| **DockerHub**    | Remote image storage |
| **Ubuntu 22.04** | Server OS inside EC2 |

---

## 🏗️ Architecture Overview
- Code hosted on **GitHub**  
- EC2 pulls repo & builds Docker image  
- App runs inside Docker container  
- Accessible on browser via **Public IP:8501**  

---

## ⚙️ Components & Configuration
| Component   | Configuration |
|-------------|---------------|
| EC2 Instance | **Streamlit-Docker-Server** |
| Instance Type | t2.medium / t3.medium |
| Storage | 20 GB gp2/gp3 |
| OS | Ubuntu 22.04 LTS |
| Security Group | Allow **22, 80, 443, 8501 (TCP)** |
| DockerHub ID | `vaibhaodocker19` |
| GitHub Repo | [streamlit_application](https://github.com/vaibhaoy19/streamlit_application.git) |

---

## 📝 Step-by-Step Deployment Procedure

### 🔹 Step 1: Launch EC2 Instance
1. Login to AWS Console → Navigate to **EC2 → Launch Instance**  
2. Choose **Ubuntu 22.04 LTS** as the AMI  
3. Instance type: **t3.medium**  
4. Storage: **20 GB gp3**  
5. Configure Security Group:  
   - **22 (SSH)** – for remote login  
   - **80 (HTTP)** – for web traffic  
   - **443 (HTTPS)** – for secure web  
   - **8501 (TCP)** – for Streamlit app  
6. Add name: `Streamlit-Docker-Server`  
7. Launch with key pair  

---

### 🔹 Step 2: Connect to EC2
```bash
ssh -i "your-key.pem" ubuntu@<your-ec2-public-ip>
🔹 Step 3: Update OS
bash
sudo apt update && sudo apt upgrade -y
🔹 Step 4: Create Project Directory & Clone Git Repo
bash
Copy code
sudo apt install git -y
mkdir my_streamlit_directory && cd my_streamlit_directory
git clone https://github.com/vaibhaoy19/streamlit_application.git
cd streamlit_application
🔹 Step 5: Install Docker
bash
Copy code
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
Check Docker installation:

bash
Copy code
docker --version
🔹 Step 6: Build Docker Image
bash
Copy code
docker build -t streamlit_application .
docker images
🔹 Step 7: Run Docker Container
bash
Copy code
docker run --name streamlit-container -d -p 8501:8501 streamlit_application
docker ps
🔹 Step 8: Access Streamlit Application
Open your browser:

cpp
Copy code
http://<your-ec2-public-ip>:8501
✅ You will see the Streamlit Web App running.

🔹 Step 9: Push Image to DockerHub
Login to DockerHub:

bash
Copy code
docker login
Tag the image:

bash
Copy code
docker tag streamlit_application vaibhaodocker19/streamlit_application:latest
Push the image:

bash
Copy code
docker push vaibhaodocker19/streamlit_application:latest
Check live image on DockerHub.

🎯 Project Summary
Framework: Streamlit

Containerization: Docker

Deployment: AWS EC2

Image Storage: DockerHub

Outcome: Portable, reproducible Streamlit app accessible via EC2 Public IP

✅ Key Highlights
Developed an interactive Streamlit web app using Python

Created a custom Dockerfile for packaging

Built & ran the app in a Docker container

Deployed successfully on AWS EC2

Published Docker image on DockerHub

Followed best DevOps practices: portability, reproducibility, scalability

🏆 Conclusion
This project demonstrates a production-like deployment pipeline for a modern Python web application. By combining Docker, AWS EC2, GitHub, and DockerHub, the deployment is:

Portable 🚀

Scalable ☁️

DevOps-ready 🔧

🔗 References
Streamlit Documentation

Docker Official Docs

AWS EC2 Guide

📸 Screenshots
👋 Welcome Page

📝 Signup Page

🏠 Dashboard
