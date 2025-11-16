# 🧾 Expense Tracker Platform – Microservices + Cloud + DevOps

A production-ready **Expense Tracker Platform** built using a modular microservices architecture with **Spring Boot**, **React Native**, **Kafka**, **Kong API Gateway**, **MySQL**, **Docker**, **Kubernetes**, **CloudFormation**, and **AWS CDK**.

This project showcases **enterprise-level engineering**, including authentication, expense management, analytics, event streaming, API gateway routing, IaC, CI/CD, and containerized deployments.

---

# 📂 Project Structure

```
root/
 ├── AWS CDK/                     # CDK IaC to deploy resources on AWS
 ├── AuthService/                 # Authentication Microservice (JWT + Spring Security)
 ├── Data Science Service/        # ML/Analytics service (Python)
 ├── ExpenseService/              # Expense CRUD Microservice
 ├── UserService/                 # User profile microservice
 ├── kafka/                       # Kafka setup + topics + brokers
 ├── kong/                        # API Gateway configs (routes, services)
 ├── mysql/                       # MySQL schema + initialization
 ├── test/                        # Testing utilities
 ├── cloudformation-template--initial-infra.yaml
 ├── cloudformation-template-deps.yaml
 ├── mysql-kafka.yml              # Docker compose for MySQL + Kafka
 ├── services.yml                 # Kubernetes service deployments
 └── README.md                    # Project Documentation
```

---

# 🏛 Architecture Overview

```
React Native App
        |
   ┌──────────────┐
   |   Kong API    |
   |    Gateway    |
   └──────────────┘
        |
 --------------------------------------------------
| AuthService      |  UserService   | ExpenseService |
 --------------------------------------------------
        |
      Kafka  <----->  Data Science Service (ML)
        |
      MySQL (DB)
        |
       AWS Cloud (CDK / CloudFormation)
```

---

# 🚀 Tech Stack

### **Frontend**
- React Native  
- Axios API client  

### **Backend Microservices**
- Spring Boot  
- Spring Security (JWT)  
- MySQL  
- Kafka Producers/Consumers  
- Python for ML analytics  

### **DevOps & Cloud**
- Docker  
- Docker Compose  
- Kubernetes (services.yml)  
- Kafka + Zookeeper  
- Kong Gateway  
- AWS CDK (IaC)  
- AWS CloudFormation  
- AWS ECS / EKS / RDS / S3  

---

# 🧩 Microservices Overview

### **1. AuthService**
- Login / Signup  
- JWT Token generation  
- Role-based access  
- Secure routes  

### **2. UserService**
- Handles user profiles  
- Preferences  
- Linked devices  
- Fetch user by ID  

### **3. ExpenseService**
- Add / Update / Delete expense  
- Categories & filtering  
- Emits Kafka events:  
  - `expense-created`  
  - `expense-updated`  
  - `expense-deleted`  

### **4. Data Science Service (Python)**
- Consumes Kafka events  
- Generates monthly analytics  
- ML-based predictions (future scope)  

---

# 🐳 Docker & Kafka Setup

Start Kafka + MySQL:

```bash
docker-compose -f mysql-kafka.yml up -d
```

Build microservices:

```bash
docker build -t auth-service ./AuthService
docker build -t user-service ./UserService
docker build -t expense-service ./ExpenseService
docker build -t analytics-service ./Data Science Service
```

---

# ☸️ Kubernetes Deployment

Deploy services:

```bash
kubectl apply -f services.yml
```

Verify deployment:

```bash
kubectl get pods
kubectl get svc
```

---

# 🌐 Kong API Gateway

Folder: `/kong`

Contains configs for:
- Routes
- Services
- Rate-limiting (optional)
- Route forwarding to microservices

Apply config:

```bash
deck sync
```

---

# 🛠 AWS Deployment (CDK)

Navigate to CDK folder:

```bash
cd "AWS CDK"
cdk bootstrap
cdk deploy
```

CDK Deploys:
- VPC  
- RDS MySQL  
- ECS/EKS cluster  
- Security groups  
- S3 buckets  
- CloudWatch logs  

---

# 🗄 Environment Variables

### Common

```
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=yourpassword
KAFKA_BOOTSTRAP_SERVERS=localhost:9092
JWT_SECRET=your_secret
```

---

# 🧪 Testing

Run Java tests:

```bash
./mvnw test
```

Run Python tests:

```bash
pytest
```

---

# 📈 Future Enhancements

- AI insights on spending  
- Anomaly detection  
- OCR for scanning receipts  
- Multi-currency support  
- Push notifications  


