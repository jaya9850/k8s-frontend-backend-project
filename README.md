
# 🚀 Kubernetes Frontend + Backend + MongoDB + Mongo Express Project

This project demonstrates a complete **Kubernetes-based full-stack application** consisting of:

- **Frontend Application**
- **Backend API**
- **MongoDB Database**
- **Mongo Express UI** for MongoDB management

All components are deployed using **Deployments**, **Services**, and **ConfigMaps** on a Kubernetes cluster.

---

## 📌 Project Architecture

Below is the high-level architecture of this project:

```

Frontend (Node/React/etc.)
|
v
Backend API  <------>  MongoDB
|
v
Mongo Express UI (Port 30000)

````

---

## 🖥️ Mongo Express UI – Deployment Screenshots

### ✅ **Mongo Express Home Page**

![Mongo Express Screenshot](/mnt/data/Screenshot 2025-11-17 141810.png)

---

### 📂 **Collection View (users collection)**

![Mongo Collection Screenshot](/mnt/data/Screenshot 2025-11-17 142446.png)

---

## 📦 Kubernetes Components Used

### **1️⃣ MongoDB Deployment & Service**
- Persistent storage using PVC
- Environment variables for DB config
- ClusterIP service for internal access

### **2️⃣ Mongo Express Deployment & NodePort Service**
- Connected to MongoDB via internal DNS
- Exposed externally on NodePort **30000**

### **3️⃣ Backend Deployment & Service**
- Communicates with MongoDB
- Exposed via ClusterIP

### **4️⃣ Frontend Deployment & Service**
- Communicates with backend service
- Exposed via NodePort

---

## 🚀 How to Deploy

### **Step 1 — Apply all YAML files**
```bash
kubectl apply -f screat.yml
kubectl apply -f configmap.yaml
kubectl apply -f backend/
kubectl apply -f frontend/
````

### **Step 2 — Confirm Pods & Services**

```bash
kubectl get pods
kubectl get svc
```

### **Step 3 — Access Mongo Express**

```
http://<Node-IP>:30000
```

---

## 🧪 Test Application

### **Check backend API**

```bash
curl http://<Node-IP>:<backend-nodeport>/api
```

### **Insert Data using Mongo Express**

* Open Mongo Express from browser
* Create database → `testdb`
* Create collection → `users`
* Insert sample document

---

## 📁 Repository Structure

```
k8s-frontend-backend-project/
│── frontend/
│── backend/
│── README.md
```

---

## 🏗️ Improvements You Can Add Later

* Ingress + SSL
* Horizontal Pod Autoscaling
* Prometheus + Grafana monitoring
* CI/CD pipeline (Jenkins / GitHub Actions)

---

## ❤️ Author

**Pratiksha Bhosale**
DevOps | AWS | Kubernetes | Docker | Linux


