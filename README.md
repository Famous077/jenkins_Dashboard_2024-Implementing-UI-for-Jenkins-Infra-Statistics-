# jenkins_GSoc 2024 project
#Implementing-UI-for-Jenkins-Infra-Statistics
# Open Source project of Jenkins

This repo covers the Jenkins Open Source 2024 project “Metric Dashboard of CI/CD”, which modernizes the Jenkins Infra Statistics dashboard. It focuses on visualizing infrastructure metrics—such as build performance and usage data—through an improved UI built for stats.jenkins.io.

# Jenkins CI/CD Dashboard – OJT Project
This project focuses on building a **custom Jenkins dashboard** that visualizes key CI/CD pipeline metrics such as build duration, queue time, and build outcomes (success, failure, aborted, unstable).  
The goal is to provide a cleaner, data-driven UI for analyzing Jenkins performance.

---

## 📌 Key Features
-  **Build Duration Trend** (Line Chart)
-  **Job Comparison** (Bar Chart)
-  **Success / Failure Distribution** (Pie Chart)
-  **Queue Time vs Execution Time**
-  **Fastest & Slowest Pipelines**
-  Clean and simple UI using **Chart.js**

---

## 🔧 Tools & Tech Stack
- **Jenkins (WAR)**
- **JDK + Maven**
- **HTML, CSS, JavaScript**
- **Chart.js**
- **Git, GitHub, VS Code**
- **Figma for UI planning**

---

##  Jenkins Data Workflow (Used for Dashboard)
Below is the exact workflow I studied and implemented while extracting metrics:

       ┌──────────────────┐
       │   Source Code     │
       │ (GitHub/Repo)     │
       └────────┬─────────┘
                │ Trigger (Commit/Webhook)
                ▼
       ┌──────────────────┐
       │   Jenkins Job     │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │   Scheduler       │
       └────────┬─────────┘
                │ Places build in queue
                ▼
       ┌──────────────────┐
       │   Queue Stage     │
       └────────┬─────────┘
                │ Wait for executor
                ▼
       ┌──────────────────┐
       │  Executor Node    │
       └────────┬─────────┘
                │ Runs pipeline stages
                ▼
       ┌──────────────────┐
       │   Build Result    │
       │ (Success/Fail/…)  │
       └────────┬─────────┘
                │ Exports logs, duration, artifacts
                ▼
       ┌──────────────────┐
       │ Dashboard Data    │
       │  (JSON/CSV)       │
       └────────┬─────────┘
                │ Visualized using Chart.js
                ▼
       ┌──────────────────┐
       │ Final Dashboard   │
       └──────────────────┘

Link of the project : [https://jenkins-dashboard-2024-implementing.vercel.app/]
## Some important PRs which we were trying to understand are given below: 

[PR1 : Related to UI of Jenkins] (https://github.com/jenkinsci/jenkins/pull/11208)
[PR2 : Related to Workflow of Jenkins] (https://github.com/jenkinsci/jenkins/pull/11230/files)
[PR3]: (https://github.com/jenkinsci/jenkins/pull/11306)
[PR4] : (https://github.com/jenkinsci/jenkins/pull/9667)
