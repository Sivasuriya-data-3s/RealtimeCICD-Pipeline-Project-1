# 🚀 Jenkins CI/CD Pipeline Project  

This project demonstrates a **Jenkins CI/CD pipeline** integrated with **GitHub, SonarQube, Maven, Dependency-Check, and Docker** to automate building, testing, analyzing, and deploying applications.  

---

## 📌 Project Workflow  

### 1. **Repository (GitHub)**  
- Source code is hosted in GitHub.  
- Jenkins pulls the latest code via **Git Checkout** whenever changes are pushed.  

### 2. **CI Pipeline (Continuous Integration)**  
The CI pipeline is handled by **Jenkins** and includes:  
- **SonarQube Analysis** → Code quality and static code analysis.  
- **Dependency-Check** → Scans for vulnerable dependencies.  
- **Maven Build** → Compiles and packages the application.  
- **Docker Build** → Creates a Docker image of the application.  

### 3. **Triggering CD Pipeline**  
- Once the Docker image is built, Jenkins **triggers the CD pipeline**.  

### 4. **CD Pipeline (Continuous Deployment)**  
- Jenkins pulls the Docker image and deploys it into a containerized environment.  
- The deployed application can be accessed via a web interface.  

---

## 🛠️ Tools & Technologies  

- **GitHub** → Source code repository  
- **Jenkins** → CI/CD automation server  
- **SonarQube** → Code quality analysis  
- **Dependency-Check** → Vulnerability scanning  
- **Maven** → Build automation tool  
- **Docker** → Containerization platform  

---

## ⚙️ Setup Instructions  

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Jenkins Setup**  
   - Install Jenkins and required plugins:  
     - GitHub  
     - Maven Integration  
     - SonarQube Scanner  
     - OWASP Dependency-Check  
     - Docker Pipeline  
   - Configure Jenkins global tools:  
     - JDK  
     - Maven  
     - SonarQube  

3. **SonarQube Setup**  
   - Run SonarQube locally via Docker:  
     ```bash
     docker run -d --name sonarqube -p 9000:9000 sonarqube
     ```  

4. **Pipeline Configuration**  
   - Create a new Jenkins pipeline job.  
   - Point it to this repository’s `Jenkinsfile`.  

5. **Deployment**  
   - Jenkins builds a Docker image.  
   - The CD pipeline deploys the container.  
   - Access the app at `http://localhost:<port>`.  

---

## 📂 Repository Structure  

```
.
├── src/                # Application source code
├── pom.xml             # Maven configuration
├── Jenkinsfile         # Jenkins pipeline definition
├── Dockerfile          # Docker image build file
└── README.md           # Project documentation
```

---

## ✅ CI/CD Pipeline Stages  

1. **Checkout** → Pulls latest code from GitHub  
2. **Build** → Maven compiles & packages app  
3. **Static Code Analysis** → SonarQube scan  
4. **Dependency Scan** → OWASP dependency-check  
5. **Docker Build & Push** → Builds Docker image  
6. **Deploy** → Runs the Docker container  

---

## 📸 Architecture Diagram  

![Pipeline Diagram](./Screenshot%202025-09-25%20144441.png)  

---

## 🔮 Future Improvements  
- Add automated testing (JUnit/Mockito).  
- Push Docker images to Docker Hub.  
- Deploy to Kubernetes cluster.  
- Enable GitHub Actions for hybrid CI/CD.  
