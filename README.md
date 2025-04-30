This repository contains the codes for the Text Embeddings through Qdrant and Milvus vectors. 
Below are the installation commands that and can be run in any terminal for the installation of the Docker, Qdrant and Milvus

Install Docker Desktop on Windows

Ensure that the option to use WSL 2 (Windows Subsystem for Linux) is selected during installation for optimal performance.

Verify Installation: Open PowerShell or Command Prompt.

Run: docker --version

Next Run Qdrant with Docker

Pull the Qdrant Docker Image: In PowerShell or Command Prompt, execute: docker pull qdrant/qdrant

Run the Qdrant Container: Choose a directory on your system to store Qdrant data, e.g., C:\qdrant\data.

Run the container with: docker run -d --name qdrant -p 6333:6333 -v C:\qdrant\data:/qdrant/storage qdrant/qdrant

  -d: Runs the container in detached mode.
  
  --name qdrant: Names the container "qdrant".
  
  -p 6333:6333: Maps port 6333 of the container to port 6333 on your host.
  
  -v C:\qdrant\data:/qdrant/storage: Mounts the host directory C:\qdrant\data to the container's /qdrant/storage directory for data persistence.
  
Verify the Qdrant Container is Running:

Run: docker ps

Next up Setting up Milvus using Docker

Install Docker & Docker Compose

Make sure Docker and Docker Compose are installed:

Install Docker: curl -fsSL https://get.docker.com -o get-docker.sh

  sh get-docker.sh
  
Install Docker Compose (if not bundled)

  sudo apt install docker-compose
  
Pull Milvus Docker Compose File, Milvus provides ready-to-use docker-compose files.

Clone the Milvus repo: git clone https://github.com/milvus-io/milvus.git

  cd milvus/deployments/docker-compose
  
Start Milvus

  docker-compose up -d
Verify Running Containers: docker ps 
