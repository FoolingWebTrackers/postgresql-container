# PostgreSQL Docker Setup
A Docker Compose setup for PostgreSQL with persistent data and automatic initialization.

## Features
- **Data Persistence:** Stores data on the host machine. 
- **Database Initialization:** Runs `init/db_init.sql` on the first startup. 
- **Health Check:** Ensures PostgreSQL is ready. Can be checked with `docker ps`

## **Setup**

1. **Clone the Repository**  
  ```bash
  git clone https://github.com/FoolingWebTrackers/postgresql-container.git
  cd postgresql-container
  ```
2. **Add Environment Variables** \
Create a .env file:
  ```env
  POSTGRES_USER=jester
  POSTGRES_PASSWORD=your_password
  POSTGRES_DB=jester-db
  ```
3. **Start the Container**
  ```bash
  docker-compose up -d
  ```

4. **Make sure everything works**
  ```bash
  docker ps
  ```

5. **Make sure you have a healthy container**
  ```bash
  CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS                    PORTS                                       NAMES
  ace74e51b26d   postgres:latest   "docker-entrypoint.s…"   17 minutes ago   Up 17 minutes (healthy)   0.0.0.0:5432->5432/tcp, :::5432->5432/tcp   postgres_container
  ```
  STATUS should be healthy

### Stop the container
  ```bash
  docker-compose down
  ```
### Check logs
```bash
docker logs postgres_container 
```

## Data Persistence

Data is stored in the data/ directory and remains after stopping the container.
