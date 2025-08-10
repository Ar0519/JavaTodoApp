# **JavaTodoApp**

A simple yet powerful To-Do application built in **Java**, containerized using **Docker**, and deployed on **AWS EC2** for cloud access.

---

## **📌 Features**
- Add, view, and delete tasks from the list.
- Lightweight Java CLI application.
- Fully containerized for consistent deployments.
- Hosted on AWS EC2 with public access.

---

## **🛠 Tech Stack**
- **Java 20** (Core Java application logic)
- **Docker** (Containerization)
- **AWS EC2** (Cloud hosting)
- **Git/GitHub** (Version control)

---

## **📂 Project Structure**
```
JavaTodoApp/
│-- Dockerfile
│-- TodoApp.java
│-- README.md
```

---

## **🚀 Run Locally**
### 1. Clone the Repository
```bash
git clone https://github.com/Ar0519/JavaTodoApp.git
cd JavaTodoApp
```

### 2. Build the Docker Image
```bash
docker build -t java-todo-app .
```

### 3. Run the Container
```bash
docker run --rm -it java-todo-app
```

---

## **☁ Deploying to AWS EC2**
### **Architecture Overview**
```
[ Developer Laptop ]
       |
       v
[ GitHub Repository ] ---> [ AWS EC2 Instance (Linux) ]
                                  |
                                  v
                           [ Docker Engine ]
                                  |
                                  v
                           [ JavaTodoApp Container ]
```

**Flow:**
1. Code is pushed to GitHub.
2. AWS EC2 pulls the code from GitHub.
3. Docker builds the container on EC2.
4. The app runs inside a container, accessible via SSH or API endpoint.

---

### **AWS Deployment Steps**
1. **Launch EC2 Instance**
   - OS: Amazon Linux 2 or Ubuntu
   - Instance Type: t2.micro (Free tier)
   - Enable ports: **22 (SSH)** and **80 (HTTP)**.

2. **Install Docker on EC2**
```bash
sudo apt update && sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

3. **Clone the Repo**
```bash
git clone https://github.com/Ar0519/JavaTodoApp.git
cd JavaTodoApp
```

4. **Build & Run**
```bash
sudo docker build -t java-todo-app .
sudo docker run --rm -it java-todo-app
```

---

## **📸 Example Architecture Diagram**
*(You can replace this with an image in the future)*

```
  ┌────────────────────┐
  │ Developer Machine  │
  └───────┬────────────┘
          │ Push Code
          ▼
  ┌────────────────────┐
  │  GitHub Repository │
  └───────┬────────────┘
          │ Pull Code
          ▼
  ┌────────────────────┐
  │ AWS EC2 Instance   │
  │  + Docker Engine   │
  └───────┬────────────┘
          │ Run Container
          ▼
  ┌────────────────────┐
  │ JavaTodoApp (CLI)  │
  └────────────────────┘
```

---

## **📜 License**
This project is licensed under the MIT License.
