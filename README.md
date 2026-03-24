End-to-End CI/CD Pipeline: Node.js on AWS EC2 📌 Overview This project demonstrates a fully automated CI/CD pipeline designed to streamline the deployment of a Node.js application. By leveraging Jenkins for orchestration, Docker for containerization, and AWS EC2 for scalable infrastructure, this pipeline ensures that every code change is automatically tested, built, and deployed with zero manual intervention.

🏗 Architecture Source Control: Developer pushes code to GitHub.

Continuous Integration: Jenkins pulls the latest code and triggers a build.

Containerization: Jenkins builds a Docker Image using the project's Dockerfile.

Continuous Deployment: Jenkins runs the Docker container on an AWS EC2 instance, mapping the application to port 3000.

🛠 Technologies Used Infrastructure: AWS EC2 (Ubuntu 22.04 LTS)

CI/CD Tool: Jenkins

Containerization: Docker

Application Stack: Node.js, Express

Source Control: GitHub

Security: AWS Security Groups, SSH

🚀 Pipeline StagesThe pipeline is defined in a Jenkinsfile and consists of three primary stages:StageDescriptionCloneFetches the latest source code from the GitHub repository.BuildBuilds a new Docker image tagged with the latest version.RunStops existing containers and launches a new container with port mapping 3000:3000.

🔧 Setup & Installation

AWS Infrastructure Launch an EC2 Instance (Ubuntu).
Edit Inbound Rules in the Security Group:

SSH (22) - For remote access.

HTTP (8080) - For Jenkins Dashboard.

Custom TCP (3000) - For the Node.js application.

Install Dependencies Connect to your EC2 via SSH and run:
Bash

Install Docker
sudo apt update && sudo apt install docker.io -y sudo usermod -aG docker $USER && newgrp docker

Install Jenkins
sudo apt install openjdk-17-jre -y curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null sudo apt update && sudo apt install jenkins -y

Gemini said This is a professional, high-quality README.md template based on your project description. It uses a clean structure, clear icons, and technical depth to make it stand out to recruiters and fellow developers.

End-to-End CI/CD Pipeline: Node.js on AWS EC2 📌 Overview This project demonstrates a fully automated CI/CD pipeline designed to streamline the deployment of a Node.js application. By leveraging Jenkins for orchestration, Docker for containerization, and AWS EC2 for scalable infrastructure, this pipeline ensures that every code change is automatically tested, built, and deployed with zero manual intervention.

🏗 Architecture Source Control: Developer pushes code to GitHub.

Continuous Integration: Jenkins pulls the latest code and triggers a build.

Containerization: Jenkins builds a Docker Image using the project's Dockerfile.

Continuous Deployment: Jenkins runs the Docker container on an AWS EC2 instance, mapping the application to port 3000.

🛠 Technologies Used Infrastructure: AWS EC2 (Ubuntu 22.04 LTS)

CI/CD Tool: Jenkins

Containerization: Docker

Application Stack: Node.js, Express

Source Control: GitHub

Security: AWS Security Groups, SSH

🚀 Pipeline Stages The pipeline is defined in a Jenkinsfile and consists of three primary stages:

Stage Description Clone Fetches the latest source code from the GitHub repository. Build Builds a new Docker image tagged with the latest version. Run Stops existing containers and launches a new container with port mapping 3000:3000. 🔧 Setup & Installation

AWS Infrastructure Launch an EC2 Instance (Ubuntu).
Edit Inbound Rules in the Security Group:

SSH (22) - For remote access.

HTTP (8080) - For Jenkins Dashboard.

Custom TCP (3000) - For the Node.js application.

Install Dependencies Connect to your EC2 via SSH and run:
Bash

Install Docker
sudo apt update && sudo apt install docker.io -y sudo usermod -aG docker $USER && newgrp docker

Install Jenkins
sudo apt install openjdk-17-jre -y curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null sudo apt update && sudo apt install jenkins -y 3. Jenkins Configuration Access Jenkins at http://:8080.

Install the Docker Pipeline plugin.

Add the jenkins user to the docker group: sudo usermod -aG docker jenkins && sudo systemctl restart jenkins

📈 Results Reliability: Eliminated manual configuration errors by using containerized environments.

Efficiency: Reduced deployment time from minutes to seconds.

Scalability: The application is easily portable to any environment running Docker.
