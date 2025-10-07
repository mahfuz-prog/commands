# Docker Commands

## Images
#### 🔹 Pull an Image
`docker pull <image_name>`
#### 🔹 List images
`docker images`
#### 🔹 Remove images
`docker rmi <image_name>`
#### 🔹 remove unused images
`docker image prune`
#### 🔹 Build an image from a Dockerfile
`docker build -t <image_name>:<version>`

#### 🔹 Dockerfile
```sh
FROM python:3.11-slim

# Set the working directory inside container
WORKDIR /url-shortner

# Install dependencies first (for Docker caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the app code
COPY app/ app/

# Expose FastAPI port
EXPOSE 8000

# Run the app
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```
#### 🔹 Create application layer Docker image and run container
```sh
docker build -t url-shortner:latest .

docker run -d --name url-shortner-app --env-file .env -p8000:8000 url-shortner
```


## Container
#### 🔹 Container all information
`docker inspect <container_name>`
#### 🔹 List all Local containers (running & stopped)
`docker ps -a`
#### 🔹 Running containers
`docker ps`
#### 🔹 Create & run a new container
`docker run <image_name>`
#### 🔹 Run container in background
`docker run -d <image_name>`
#### 🔹 Run container with custom name
`docker run -it --name <container_name> <image_name>`
#### 🔹 Port Binding in container
`docker run --name <set_name> -p<host_port>:<container_port> <image_name>`

## Troubleshoot
#### 🔹 Fetch logs of a container
`docker logs <container_name> (or <container_id)`
#### 🔹 Open shell inside running container
```sh
docker exec -it ubuntu /bin/bash
docker exec -it redis redis-cli
docker exec -it <container_name> sh
```

## Network
#### 🔹 List all networks
`docker network ls`
#### 🔹 Create a network
`docker network create <network_name>`
#### 🔹 Remove a network
`docker network rm <network_name>`
#### 🔹 Remove all unused networks
`docker network prune`

## Docker Compose
#### 🔹 create container
```sh
docker compose up -d
docker compose up --build
docker compose -f filename.yml up -d
```
#### 🔹 remove container
```sh
docker compose down
docker compose -f filename.yml down
```

## Docker volumes
Create a folder on host machine. this apporach mount host folder to container folder.
After that the container data will save on host machine folder. If the container deleted
host machine data still persist.

#### 🔹 test volumes
```sh
# -v host_path:container_path

docker run -it -v C:\Users\User\Desktop\test:/test/data ubuntu /bin/bash

cd test/data
touch a.txt
touch b.txt
```

#### 🔹 compose volumes
```sh
services:
  postgresdb:
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```