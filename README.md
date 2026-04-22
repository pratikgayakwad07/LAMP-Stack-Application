# LAMP-Stack-Application

# 🚀 Dockerized LAMP + Spring Boot Application

This project demonstrates how to containerize and run a **multi-stack application** using Docker and Docker Compose:

* 🐘 LAMP Stack (Linux + Apache + MySQL + PHP)
* ☕ Spring Boot (Maven-based Java application)
* 🐬 MySQL Database
* 📦 Docker Compose orchestration

---

# 📁 Project Structure

```
docker-multi-stack/
│
├── lamp-stack/
│   ├── Dockerfile
│   └── index.php
│
├── springboot-app/
│   └── java-spring-boot-app/
│       ├── Dockerfile
│       └── (Spring Boot source code)
│
└── docker-compose.yml
```

---

# ⚙️ Prerequisites

Make sure you have installed:

* Docker
* Docker Compose
* Git

---

# 🔧 Setup Instructions (Step-by-Step)

## 1️⃣ Clone Repository

```
mkdir LAMP-stack-application
cd LAMP-stack-application
mkdir lamp-stack
vim Dockerfile
vim index.php

mkdir springboot-app
cd springboot-app
git clone https://github.com/pratikgayakwad07/java-spring-boot-app.git
cd java-spring-boot-app
vim dockerfile
```

---

## 2️⃣ Build Containers

```
docker-compose build
```

---

## 3️⃣ Run Containers

```
docker-compose up -d
```

---

## 4️⃣ Verify Running Containers

```
docker ps
```

---

# 🌐 Access Applications

### ✅ LAMP Stack

```
http://public-ip:8081
```

Expected Output:

```
Hello from LAMP Stack 🚀
```

---

### ✅ Spring Boot App

```
http://publicip:8080
```

---

# 🐬 MySQL Configuration

| Property | Value |
| -------- | ----- |
| Host     | mysql |
| Port     | 3306  |
| Database | mydb  |
| Username | root  |
| Password | root  |

---

# 🔌 Spring Boot Database Configuration

Update `application.properties`:

```
spring.datasource.url=jdbc:mysql://mysql:3306/mydb
spring.datasource.username=root
spring.datasource.password=root
```

---

# 🐳 Docker Details

## LAMP Dockerfile

* Base Image: `php:8.2-apache`
* Installs MySQL extension
* Serves PHP app via Apache

---

## Spring Boot Dockerfile

* Multi-stage build:

  * Stage 1: Maven build
  * Stage 2: Run JAR with Java 17

---

## Docker Compose Services

* mysql → Database
* lamp → PHP + Apache
* springboot → Java app

---

# ⚠️ Troubleshooting

## ❌ Container not starting

```
docker-compose logs
```

---

## ❌ Spring Boot issues

```
docker logs springboot_app
```

---

## ❌ MySQL connection error

✔ Use:

```
mysql
```

---

# 📦 Stop Containers

```
docker-compose down
```

---

