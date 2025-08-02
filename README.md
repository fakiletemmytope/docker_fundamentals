# Containerize and Set up CI pipeline for the Dream Vacation App

This project contains the Dockerfile(s) for the frontend and backend of the Dream Vacations application, and orchestrated with Docker Compose for seamless local development and deployment. And the workflows for the continuous integration of the backend and frontend application set up

## Objectives

1. Containerize the Dream Vacation App using Docker and Docker Compose. By the end of this task, your application should run end-to-end using isolated, reproducible containers.

2. Set up the workflows for the continuous integration of both the backend and the frontend applications.

### Tech Stack

1. Frontend: React.js
2. Backend: Node.js (Express or similar)
3. Containerization: Docker
4. Orchestration: Docker Compose

### Pre-requisites

1. Docker
2. Docker compose


## Containerization of the frontend and Backend Application

1. Clone the app

   ```bash
   git clone https://github.com/your-username/dream-vacations.git
   cd dream-vacations
   ```
2. Write the Dockerfile configuration to build both the frontend and backend docker images

* **Frontend Dockerfile**

  Configures and builds the React app into a production-ready container.
* **Backend Dockerfile**

  Sets up the Node.js server and prepares it to run inside a container.

3. Build and tag the image

   ```bash
   cd frontend
   docker buildx build -t <docker-repo>/<image-name> .
   cd backend
   docker buildx build -t <docker-repo>/<image-name> .
   ```
4. Write a `docker-compose.yaml` file to:

* Define both the frontend, backend and database services.
* Specify the ports for each service.
* Set up a shared Docker network to allow communication between the three containers.
* Set up a volume for the database to ensure data persists when the container stops working

5. Run the Application

   Docker Compose to build and run the containers

   ```bash
   docker compose up -d
   ```

## Continuous Integration Workflow
