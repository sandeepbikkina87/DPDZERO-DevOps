==============================  DevOps Intern Assignment: Nginx Reverse Proxy + Docker ==================================

>> Multi-Service Dockerized Application

This project contains multiple services managed using Docker Compose:

>> service_1 : A Go backend service
>> service_2 : A Python backend service (FastAPI or Flask)
>> nginx : A reverse proxy for routing between services

---

>> Project Structure


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



>> Prerequisites

Make sure you have the following installed:

- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [git](https://git-scm.com/downloads/linux)

Check Docker installation:

docker --version
docker compsose version
git --version


>>  How to Run the Project

1. Clone the Repository

   git clone <your-repo-url>
   cd <project-directory>

2. Build and Start All Services
   
   docker-compose up -d # -d for detach mode

>> This command will:

- Build Docker images for each service
- Start the containers for service_1, service_2, and nginx

3. View Running Containers

   docker ps  #view running containers
   docker ps -a  #view running/existing containers

4. Access the Application

>> Once the containers are up and running, open your browser and go to.

http://localhost:8080 # nginx
http://localhost:8080/service1/ping # golang
http://localhost:8080/service2/ping # python

5. Stopping the Project

>>To stop all containers and remove networks

docker-compose down

>> View Logs from All Services

docker compose logs -f


