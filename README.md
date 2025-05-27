# 🚀 Jenkins CI/CD Pipeline Demo

Welcome to the **Jenkins CI/CD Pipeline Demo Project**!  
This project showcases how to set up a simple Continuous Integration & Continuous Deployment (CI/CD) pipeline using **Jenkins**, **Docker**, and **GitHub**.

---

## 🧩 Tech Stack

- 🐳 Docker  
- 🧪 Jenkins  
- 🧾 Jenkinsfile (Declarative Pipeline Syntax)  
- 🐙 Git & GitHub

---

## 🎯 Project Objectives

✅ Launch Jenkins using Docker  
✅ Configure and Unlock Jenkins  
✅ Create a Multistage Pipeline: **Build → Test → Deploy**  
✅ Connect Jenkins to GitHub for SCM  
✅ Trigger Pipeline via Git Push  
✅ Track status in Jenkins Dashboard  

---

## 📦 Step-by-Step Setup

### 🐳 Step 1: Run Jenkins in Docker

```bash
docker run -d \
  -p 8080:8080 -p 50000:50000 \
  --name jenkins-container \
  -v jenkins_home:/var/jenkins_home \
  jenkins/jenkins:lts
```

📍 Jenkins will be available at: [http://localhost:8080](http://localhost:8080)

---

### 🔐 Step 2: Unlock Jenkins

Retrieve the initial admin password:

```bash
docker exec jenkins-container cat /var/jenkins_home/secrets/initialAdminPassword
```

Paste it in the browser to complete setup → Install Suggested Plugins

---

### 🛠️ Step 3: Create Jenkins Pipeline Job

1. Go to Jenkins dashboard → **New Item**
2. Name it: `Simple-CICD-Pipeline`
3. Choose: `Pipeline` → OK
4. Scroll to **Pipeline → Definition**: Select **Pipeline script from SCM**
5. Set:
   - **SCM**: Git  
   - **Repo URL**:  
     ```
     https://github.com/yasvanthrajan/jenkins-pipeline-demo.git
     ```
   - **Branch**: `main`

---

## 📝 Jenkinsfile (Pipeline Script)

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }
}
```

✅ Copy and place this in a file named `Jenkinsfile` in your GitHub repo.

---

## 📤 Step 4: Push Jenkinsfile to GitHub

```bash
git clone https://github.com/yasvanthrajan/jenkins-pipeline-demo.git
cd jenkins-pipeline-demo
git add Jenkinsfile
git commit -m "Add basic Jenkins pipeline"
git push origin main
```

---

## ✅ Result: Successful Build

- Jenkins pulled the `main` branch
- Ran through the pipeline stages:
  - ✔️ Build
  - ✔️ Test
  - ✔️ Deploy
- Console Output shows all steps executed

---

## 📸 Screenshots

> 📌 Add the following screenshots before submission:
- Jenkins Dashboard showing successful build
- Console output showing all 3 stages
- GitHub repo with `Jenkinsfile`

---

## 🔗 GitHub Repository

[📂 Click here to open the repo](https://github.com/yasvanthrajan/jenkins-pipeline-demo)

---

## 🙌 Acknowledgments

Thanks to the [PEP Program] for guidance and motivation!  
Built with **Yasvanth Rajan**

---

## 📝 Submission Instructions

Include the following in your submission form:
- ✅ GitHub Repo Link
- ✅ Screenshot of Jenkins pipeline run
- ✅ This `README.md`

---
