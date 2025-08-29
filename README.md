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

## 📝 Step-by-Step Deployment

### 1️⃣ Launch EC2 Instance
- Select **Ubuntu 22.04 LTS**  
- Instance type: `t3.medium`  
- Storage: 20 GB  
- Open ports: **22, 80, 443, 8501**  

### 2️⃣ Connect to EC2
```bash
ssh -i "key.pem" ubuntu@<your-ec2-public-ip>
