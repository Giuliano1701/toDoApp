# ToDoApp

This is a multi-service ToDo application, orchestrated using Docker Compose. It consists of a frontend client, a ToDo API, an authentication service, and a PostgreSQL database.

## Services

- **Client**: A web-based frontend application for interacting with the ToDo services. Two instances are available.
- **ToDo API**: A backend service that manages ToDo items.
- **Auth Service**: A backend service responsible for user authentication and authorization.
- **PostgreSQL Database**: A relational database used by both the ToDo API and Auth Service.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Make sure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Installation

1.  **Clone the repository (if applicable):**
    ```bash
    git clone <repository_url>
    cd toDoApp
    ```
    (Assuming you are already in the `toDoApp` directory)

2.  **Build and run the services using Docker Compose:**
    This command will build the Docker images for the client, todo_api, and auth_service, and then start all the services, including the PostgreSQL database.

    ```bash
    docker-compose up --build -d
    ```
    The `-d` flag runs the services in detached mode (in the background).

3.  **Verify services are running:**
    ```bash
    docker-compose ps
    ```
    You should see all services listed with a `Up` status.

### Accessing the Application

Once all services are up and running:

-   **Client (Frontend) 1**: Access the main application in your web browser at `http://localhost:8080`
-   **Client (Frontend) 2**: Access the second instance of the application in your web browser at `http://localhost:8081`
-   **ToDo API**: The API will be available internally to the client services and externally at `http://localhost:5001`
-   **Auth Service**: The authentication service will be available internally to the client services and externally at `http://localhost:5002`

## Stopping the Application

To stop all running services and remove the containers, networks, and volumes created by `docker-compose up`:

```bash
docker-compose down -v
```
The `-v` flag also removes the `pgdata` volume, which means your database data will be lost. If you want to preserve the database data, omit the `-v` flag.

## Project Structure

```
.
├── .gitignore
├── actual_requirements.txt
├── docker-compose.yml
├── client/
│   ├── app.js
│   ├── Dockerfile
│   ├── favicon.svg
│   ├── index.html
│   └── style.css
└── server/
    ├── auth_service/
    │   ├── app.py
    │   ├── Dockerfile
    │   └── requirements.txt
    └── todo_api/
        ├── app.py
        ├── Dockerfile
        └── requirements.txt
```
