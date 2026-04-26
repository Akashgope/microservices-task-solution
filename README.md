
## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!


**Microservices with Docker**
This project contains four microservices built with Node.js/Express and containerized using Docker. The services are:

User Service – port 3000, endpoint /users

Product Service – port 3001, endpoint /products

Order Service – port 3002, endpoint /orders

Gateway Service – port 8080, root endpoint /

All services are orchestrated with Docker Compose.

🚀 Setup Instructions
Prerequisites
Docker installed (Download)

Docker Compose (comes with Docker Desktop)

Steps to Run
Clone the repository (or unzip the submission folder):

bash
git clone https://github.com/Akashgope/microservices-task-solution.git
cd microservices-task-solution/submission
Build and start all containers:

bash
docker-compose up --build
The first build may take a minute. Once finished, you’ll see log lines like:

text
user-service-1  | User Service running on port 3000
product-service-1 | Product Service running on port 3001
order-service-1  | Order Service running on port 3002
gateway-service-1 | Gateway Service running on port 8080
Run in detached mode (optional):

bash
docker-compose up -d
Stop the services:

bash
docker-compose down
🧪 How to Test Each Service
Once the containers are running, open a new terminal and use curl or a web browser.

Service	Command	Expected Response
User Service	curl http://localhost:3000/users	{"message":"User Service OK"}
Product Service	curl http://localhost:3001/products	{"message":"Product Service OK"}
Order Service	curl http://localhost:3002/orders	{"message":"Order Service OK"}
Gateway Service	curl http://localhost:8080/	{"message":"Gateway Service OK"}
You can also open these URLs directly in your browser.

Example (Terminal)
bash
$ curl http://localhost:3000/users
{"message":"User Service OK"}
🛠️ Basic Troubleshooting Tips
Problem	Solution
docker-compose: command not found	Install Docker Desktop and ensure Docker is running.
no configuration file provided	Navigate to the folder containing docker-compose.yml before running the command.
Port already in use (e.g., bind: address already in use)	Stop the application using that port: sudo lsof -i :3000 (find PID) then kill <PID>, or change the host port in docker-compose.yml.
Container exits immediately with code 1	Run docker-compose logs <service-name> (e.g., docker-compose logs user-service) to see the error log. Common: missing app.js or package.json.
curl: (7) Failed to connect to localhost port 3000	Ensure the container is running (docker ps). If not, run docker-compose up --build again.
Changes in code not reflected	Rebuild with docker-compose up --build to refresh the image.
📸 Screenshots

<img width="573" height="106" alt="Screenshot 2026-04-26 at 9 45 19 PM" src="https://github.com/user-attachments/assets/cfdbacbd-bc86-481f-9678-3f468c149de8" />

<img width="569" height="269" alt="Screenshot 2026-04-26 at 9 46 34 PM" src="https://github.com/user-attachments/assets/dc98dff3-c1a3-499d-aeae-47ae91c2646e" />

<img width="573" height="31" alt="Screenshot 2026-04-26 at 9 47 41 PM" src="https://github.com/user-attachments/assets/9cb4fddf-76a7-4ca5-ae71-c031d8459820" />

<img width="563" height="27" alt="Screenshot 2026-04-26 at 9 47 57 PM" src="https://github.com/user-attachments/assets/63f14a7c-90d4-4d04-9593-a676057dda46" />

<img width="557" height="29" alt="Screenshot 2026-04-26 at 9 48 13 PM" src="https://github.com/user-attachments/assets/1b7ba1fd-2e79-4d48-8766-48e0de720589" />

<img width="520" height="32" alt="Screenshot 2026-04-26 at 9 48 20 PM" src="https://github.com/user-attachments/assets/4806672b-bdf8-42a6-a508-c83d130bd429" />

<img width="575" height="139" alt="Screenshot 2026-04-26 at 9 48 29 PM" src="https://github.com/user-attachments/assets/203101e1-5b3a-4376-ae7e-eab2c3d605ac" />

<img width="572" height="243" alt="Screenshot 2026-04-26 at 9 48 50 PM" src="https://github.com/user-attachments/assets/f0465173-3ba4-442f-9c8e-420f5fc99cad" />


Build & Run Terminal
https://images/docker-up-logs.png

docker ps Output
https://images/docker-ps.png

Service Testing (curl)
https://images/curl-users.png
https://images/curl-products.png
https://images/curl-orders.png
https://images/curl-gateway.png

📁 Project Structure
text
submission/
├── user-service/
│   ├── Dockerfile
│   ├── package.json
│   └── app.js
├── product-service/
│   ├── Dockerfile
│   ├── package.json
│   └── app.js
├── order-service/
│   ├── Dockerfile
│   ├── package.json
│   └── app.js
├── gateway-service/
│   ├── Dockerfile
│   ├── package.json
│   └── app.js
├── docker-compose.yml
└── README.md
✅ Submission Deliverables
Dockerfiles for all four services ✅

docker-compose.yml ✅

This README.md with documentation and screenshots ✅
