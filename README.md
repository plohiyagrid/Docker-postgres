# Docker Compose Database Setup

This repository provides a Docker Compose configuration to create a local PostgreSQL database container with environment variable support and persistent storage.

## Prerequisites

Ensure you have the following installed:

- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Setup Instructions

### 1. Clone the Repository

```sh
git clone https://github.com/plohiyagrid/Docker-postgres.git
cd DataBase
```

### 2. Configure Environment Variables

Create a `.env` file in the project root and define your database settings:

```
DB_NAME=mydatabase  
DB_USER=myuser  
DB_PASSWORD=mypassword  
DB_PORT=5432  
```

### 3. Start the Database Container

Run the following command to start the database container:

```sh
docker compose up -d
```

This will:

- ✅ Pull the PostgreSQL image
- ✅ Create and start a database container
- ✅ Use environment variables from `.env`
- ✅ Persist data using a Docker volume

### 4. Verify the Running Container

Check if the container is running:

```sh
docker ps
```

### 5. Connect to the Database

#### Using Docker CLI

```sh
docker exec -it my_database_container psql -U myuser -d mydatabase
```

### 6. Stop and Remove the Container

To stop and remove the database container:

```sh
docker compose down
```

To remove the volume (**this will delete all data!**):

```sh
docker compose down -v
```

## Notes

- The `.env` file allows easy customization without modifying `docker-compose.yml`.
- Data persists across container restarts via Docker volumes.
- Ensure you have Docker Desktop running before executing commands.
