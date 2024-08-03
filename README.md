# BookVault

## Overview
BookVault is a full-stack library management system with separate frontend and backend components. This repository provides a Docker setup for easy deployment and development.

## Setup Instructions

### Prerequisites
- Docker
- Docker Compose

### Environment Setup

1. **Create Environment Files:**
   - Navigate to the `frontend` and `backend` directories.
   - Copy the `.env.example` file to a new file named `.env` in each respective directory.

     ```sh
     cp frontend/.env.example frontend/.env
     cp backend/.env.example backend/.env
     ```

2. **Modify the `.env` files** with your configuration settings.

### Docker Setup

1. **Start Docker Compose:**
   - Run the following command from the root of the `bookvault` directory, specifying the path to your backend `.env` file:

     ```sh
     docker compose --env-file=./backend/.env up
     ```

2. **Initialize the Backend Database (First-time Setup Only):**
   - Open a new terminal and execute the following command to access the backend container's shell:

     ```sh
     docker compose --env-file=./backend/.env exec -it backend sh
     ```

   - Within the backend container's shell, run the following commands to migrate and seed the database:

     ```sh
     npm run migrate
     npm run seed:run
     ```

### Accessing the Application

- Once the setup is complete, the application should be running on [http://localhost:5173/](http://localhost:5173/).

## Repository Structure

- **frontend/**: Contains the frontend application code.
- **backend/**: Contains the backend application code.
- **docker-compose.yml**: Docker Compose configuration file to set up the application.

## Contribution Guidelines

We welcome contributions to improve BookVault. Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch with a descriptive name.
3. Make your changes.
4. Submit a pull request with a detailed description of your changes.


## Contact

For any questions or suggestions, please contact [Kalash Shrestha](mailto:kalashestha@gmail.com).

