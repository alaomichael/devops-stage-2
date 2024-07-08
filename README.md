# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

This project includes a frontend, backend, PostgreSQL database, Adminer, and Nginx Proxy Manager. The goal is to deploy these services using Docker on a GCP VM with proper configurations for domain management and secure access.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)


#### README Structure

1. **Structure**
2. **Prerequisites**
3. **Cloning the Repository**
4. **Environment Setup**
5. **Running the Application with Docker Compose**
6. **Accessing the Services**
7. **Manual Deployment Instructions**
8. **Troubleshooting**

#### 1. Structure

```markdown
## Services

- Frontend: A web application running on Node.js.
- Backend: A web API running on FastAPI.
- PostgreSQL: The database for the backend.
- Adminer: A database management tool.
- Nginx Proxy Manager: Manages the reverse proxy for frontend, backend, and other services.
```

#### 2. Prerequisites

```markdown
## Prerequisites

Before you begin, ensure you have the following installed:

- Docker
- Docker Compose
- A domain name or a free subdomain (e.g., from Afraid DNS)
- A GCP account with a VM instance set up
```

#### 3. Cloning the Repository

```markdown
## Cloning the Repository

Clone the repository to your local machine:

```sh
git clone https://github.com/alaomichael/devops-stage-2.git
cd devops-stage-2
```

#### 4. Environment Setup

```markdown
## Environment Setup

Create a `.env` file in the root directory and add the following environment variables:

```plaintext
# .env file

DATABASE_URL=postgresql://user:password@postgres:5432/dbname
NODE_ENV=production
POSTGRES_USER=user
POSTGRES_PASSWORD=password
POSTGRES_DB=dbname
```

Ensure to replace `user`, `password`, and `dbname` with your actual database credentials.

#### 5. Running the Application with Docker Compose

```markdown
## Running the Application with Docker Compose

Use Docker Compose to build and run the containers. Run the following commands in your project directory:

```sh
sudo docker-compose down
sudo docker-compose up --build -d
```

This will start the following services:

- Frontend on port 5173
- Backend on port 8000
- PostgreSQL on port 5432
- Adminer on port 8080
- Nginx Proxy Manager on ports 80, 81, and 443

#### 6. Accessing the Services

```markdown
## Accessing the Services

Once the containers are up and running, you can access the services via the following URLs:

- **Frontend**: `https://yourdomain.com`
- **Backend API**: `https://yourdomain.com/api`
- **Docs**: `https://yourdomain.com/docs`
- **Redoc**: `https://yourdomain.com/redoc`
- **Adminer**: `https://db.yourdomain.com`
- **Proxy Manager**: `https://proxy.yourdomain.com`

Ensure that your DNS records are correctly configured to point to your GCP VM's public IP address.

#### 7. Manual Deployment Instructions

```markdown
## Manual Deployment Instructions

In case you need to manually deploy the application without Docker, follow these steps:

### Frontend

1. Install Node.js and npm.
2. Navigate to the frontend directory: `cd frontend`.
3. Install dependencies: `npm install`.
4. Build the project: `npm run build`.
5. Serve the build directory using a web server like Nginx.

### Backend

1. Install Python and Poetry.
2. Navigate to the backend directory: `cd backend`.
3. Install dependencies: `poetry install`.
4. Run the application: ` poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload`.

### PostgreSQL

1. Install PostgreSQL.
2. Create a database and a user.
3. Update the `DATABASE_URL` in the backend's environment variables.

### Adminer

1. Download Adminer: `wget https://www.adminer.org/latest.php -O adminer.php`.
2. Serve Adminer using a web server like Nginx or PHP's built-in server: `php -S 0.0.0.0:8080 adminer.php`.

### Nginx Proxy

1. Install Nginx.
2. Configure Nginx to reverse proxy the frontend and backend services.
3. Enable SSL using Let's Encrypt.

#### 8. Troubleshooting

```markdown
## Troubleshooting

### Common Issues

1. **Containers not starting**:
   - Check the Docker logs for errors: `sudo docker logs <container_name>`.

2. **Services not accessible**:
   - Ensure your DNS records are correctly pointing to your GCP VM's IP.
   - Verify that the ports are open in your GCP VM's firewall settings.

3. **Database connection issues**:
   - Confirm that the database credentials in the `.env` file are correct.
   - Ensure that the PostgreSQL container is running: `sudo docker ps`.

### Contact

For further assistance, contact [devmichaelalao@gmail.com].
```
