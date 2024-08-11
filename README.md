# Django-React Docker Template

This repository provides a simple template to quickly bootstrap a Django and React project, fully dockerized for easy setup and deployment. This template includes the necessary configuration for running Django as the backend and React as the frontend within Docker containers.

## Features

- **Django**: The backend server using Django.
- **React**: The frontend built with React, bootstrapped with Create React App.
- **Docker Compose**: Simplified management of both the Django and React containers.
- **Volume Mounting**: For hot-reloading in development, allowing code changes without restarting containers.

## Prerequisites

- Docker and Docker Compose installed on your local machine.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/mateuszNadolny/react-django-docker-template.git
cd django-react-docker-template
```

### 2. Create Environment Variables

```bash
cp .env.example .env
```

### 3. Build and Start the Containers

```bash
docker-compose up --build
```
### 4. Access the Application

- Frontend (React): The React application will be available at http://localhost:5173.
- Backend (Django): The Django API will be available at http://0.0.0.0:8000.
- Admin Panel: Access the Django admin panel at http://0.0.0.0:8000/admin.

### 5. Running Commands Inside Containers

To run commands like migrations, Django shell, or npm commands, you'll need to execute them within the containers. For example:

- Django Commands:
```bash
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py createsuperuser
```

- React Commands:
```bash
docker-compose exec frontend npm install
docker-compose exec frontend npm run build
```

### 6. Stopping the Containers

To stop all running containers:

```bash
docker-compose down
```

### 7. Deployment

For production deployment, you'll need to modify the .env file to set DJANGO_DEBUG=False and make sure to use secure values for all environment variables.

You can build and run the containers in detached mode using:

```bash
docker-compose up --build -d
```

***

### Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue to discuss improvements or bugs.