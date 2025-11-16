# 📊 Expense Tracker – Full Stack (React Native + Spring Boot + Kafka + AWS)

A production-grade **Expense Tracking Application** built with a modern cloud-native architecture.  
It supports **real-time expense syncing**, **category-wise analytics**, **secure authentication**, and **scalable microservices** deployed using **Docker, Kubernetes, and AWS**.

---

## 🚀 Tech Stack

### **Frontend**
- React Native (Expo / CLI)
- Context API / Redux Toolkit
- Axios + React Query

### **Backend**
- Spring Boot (REST API)
- Spring Security + JWT
- MySQL
- Kafka (Event streaming)

### **DevOps & Cloud**
- Docker
- Kubernetes
- AWS CDK (IaC)
- AWS: EKS, RDS, S3, CloudWatch, IAM, ALB

---

## 📱 Features

### User Features
- Add/edit/delete expenses
- Category-wise filters
- Monthly analytics dashboard
- Real-time sync via Kafka
- JWT Authentication
- Multi-device syncing
- Offline support

### Backend Features
- Kafka producers/consumers
- Analytics microservice
- MySQL relational database
- Cloud-native deployment

---

## 🏗️ Architecture Overview

```
React Native App
        |
   API Gateway
        |
 ------------------------
| Spring Boot Services   |
|  - Auth Service        |
|  - Expense Service     |
|  - Analytics Consumer  |
 ------------------------
        |
   Kafka Cluster
        |
  MySQL (RDS)
        |
    AWS Cloud
```

---


---

## 🧰 Local Development Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/expense-tracker.git
cd expense-tracker
```

---

# 🖥️ Backend Setup (Spring Boot)

### 2. Create MySQL Database

```sql
CREATE DATABASE expense_tracker;
```

Update `application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/expense_tracker
    username: root
    password: yourpassword
```

---

### 3. Start Kafka Using Docker

```bash
docker-compose -f docker/kafka.yml up -d
```

---

### 4. Run Backend Services

```bash
./mvnw spring-boot:run
```

---

# 📱 Frontend Setup (React Native)

### 5. Install dependencies

```bash
cd frontend
npm install
```

### 6. Start Expo

```bash
npx expo start
```

---

# 🐳 Docker Setup

Build Docker images:

```bash
docker build -t expense-auth backend/auth-service
docker build -t expense-expense backend/expense-service
docker build -t expense-analytics backend/analytics-service
docker build -t expense-analytics backend/user-service
docker build -t expense-analytics backend/data-science-service
```

Run everything:

```bash
docker compose up -d
```

---

# ☸️ Kubernetes Deployment

Apply manifests:

```bash
kubectl apply -f kubernetes/
```

Check pods:

```bash
kubectl get pods
```

---

# ☁️ AWS CDK Deployment

### Bootstrap CDK

```bash
cd infra/cdk
cdk bootstrap
```

### Deploy Infrastructure

```bash
cdk deploy
```

This deploys:  
✔ VPC  
✔ EKS Cluster  
✔ RDS MySQL  
✔ S3 buckets  
✔ IAM roles  
✔ Application Load Balancer  

---

# 🔐 Environment Variables

### Backend `.env`

```
JWT_SECRET=your-secret-key
MYSQL_USER=root
MYSQL_PASSWORD=password
KAFKA_BOOTSTRAP_SERVERS=localhost:9092
```

### Frontend `.env`

```
API_URL=https://your-api-url.com
```

---

# 📊 Kafka Topics

| Topic Name          | Purpose                           |
|---------------------|-----------------------------------|
| expense-created     | New expense added                  |
| expense-updated     | Expense updated                    |
| expense-deleted     | Expense deleted                    |
| analytics-update    | Analytics consumer processing      |

---

# 🧪 Testing

### JUnit + Jest Tests

```bash
./mvnw test
npm test
```

---

# 🛡 Security

- JWT auth  
- BCrypt password hashing  
- AWS IAM roles  
- Private RDS & Kafka  

---

# 📈 Future Enhancements
- AI-based spending predictions  
- Budget alerts  
- OCR bill scanning  
- Multi-currency support  
- Web dashboard  



