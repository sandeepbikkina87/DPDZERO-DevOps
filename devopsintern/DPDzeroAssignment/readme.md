### 🧪 **DevOps Intern Assignment: Nginx Reverse Proxy + Docker**

# 🧩 Multi-Service Dockerized Application

This project contains multiple services managed using Docker Compose:

- **service_1**: A Go backend service
- **service_2**: A Python backend service (FastAPI or Flask)
- **nginx**: A reverse proxy for routing between services

---

## 📁 Project Structure

```
├── docker-compose.yml
├── nginx
│   ├── default.conf
│   ├── Dockerfile
│   └── README.md
├── readme.md
├── service_1
│   ├── Dockerfile
│   ├── main.go
│   └── README.md
└── service_2
    ├── app.py
    ├── Dockerfile
    ├── pyproject.toml
    ├── README.md
    └── uv.lock
```

---

## 🚀 Getting Started

### ✅ Prerequisites

Make sure you have the following installed:

- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [git](https://git-scm.com/downloads/linux)

Check Docker installation:

```bash
docker --version
docker compsose version
git --version
```

---

### 🛠 How to Run the Project

1. **Clone the Repository**

   ```bash
   git clone <your-repo-url>
   cd <project-directory>

   ```

2. **Build and Start All Services**
   ```bash
   docker-compose up --build -d # -d for detach mode
   ```

#### This command will -:

- Build Docker images for each service
- Start containers for service_1, service_2, and nginx

3. **View Running Containers**

   ```bash
   docker ps

   ```

4. **Access the Application**

##### Once the containers are up and running, open your browser and go to.

####

```bash
http://localhost # nginx
http://localhost/service1/ping # golang
http://localhost/service2/ping # python
```

---

## 🛑 Stopping the Project

### To stop all containers and remove networks

```bash
docker-compose down
```

---

## 📜 View Logs from All Services

```
docker compse logs -f

```

#### You can also view logs for a specific service:

```
docker-compose logs -f service_1
docker-compose logs -f service_2
docker-compose logs -f nginx

```

---

## 📌 Notes

### Ensure that required ports (e.g., 80, 8001, 8002) are not in use.

### Link of assignment 
```
https://docs.dpdzero.com/s/54dd25e3-7b3f-4327-92e8-34e32d8c377b#h-%E2%9C%85-requirements
https://github.com/DPDzero/devops-assignment-Q2-2025.git
```
