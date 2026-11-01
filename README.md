# Automating CI/CD Workflow for a Dockerized Flask Application Using GitHub Actions

An end-to-end Continuous Integration and Continuous Deployment (CI/CD) project that automates the testing, building, and deployment workflow of a Dockerized Flask application using GitHub Actions.

## Overview

This project demonstrates how to build an automated CI/CD pipeline for a Flask web application using GitHub Actions and Docker.

The pipeline automates the software delivery process, ensuring that application changes are tested, validated, containerized, and prepared for deployment with minimal manual intervention.

Whenever code is pushed to the repository or a pull request is created, GitHub Actions automatically executes the configured workflow to maintain application quality and consistency.

## Objectives

- Develop a Python-based web application using Flask.
- Containerize the application using Docker.
- Automate application testing through GitHub Actions.
- Implement Continuous Integration (CI) to validate code changes.
- Automate Docker image building.
- Implement Continuous Deployment (CD) to deploy the application.
- Manage credentials securely using GitHub Actions Secrets.
- Establish a reliable and repeatable software delivery workflow.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application development |
| Flask | Web application framework |
| Docker | Application containerization |
| Git & GitHub | Version control and source code management |
| GitHub Actions | CI/CD pipeline automation |
| Pytest | Automated testing |
| GitHub Secrets | Secure credential management |

## CI/CD Workflow

The project follows an automated pipeline consisting of the following stages:

### 1. Source Code Management
- Maintain application source code in GitHub.
- Use feature branches for development.
- Trigger workflows on pushes and pull requests.

### 2. Continuous Integration (CI)
- Check out the latest source code.
- Set up the required Python environment.
- Install project dependencies.
- Run code quality and validation checks.
- Execute automated tests using Pytest.
- Build the Docker image to verify containerization.

### 3. Docker Image Management
- Build a Docker image containing the Flask application and its dependencies.
- Apply appropriate image tags.
- Publish the image to a container registry when all required checks pass.

### 4. Continuous Deployment (CD)
- Trigger deployment after successful CI and image publishing.
- Authenticate securely using GitHub Secrets.
- Deploy the containerized application to the configured hosting platform.
- Verify that the deployed application is accessible.

## Project Structure

```text
DockerImage/
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
│
├── app/
│   ├── __init__.py
│   └── routes.py
│
├── tests/
│   └── test_app.py
│
├── Dockerfile
├── .dockerignore
├── .gitignore
├── requirements.txt
├── README.md
└── .venv/
```

*The structure above represents the intended organization; adjust filenames and folders to match the actual implementation. Do not commit the `.venv/` directory.*

## Getting Started

### Prerequisites

Install the following tools before running the project:

- Python 3.14+
- Git
- Docker Desktop
- A GitHub account

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Create and Activate the Virtual Environment

Using Conda:

```bash
conda create --prefix .venv python=3.14 pip -y
conda activate ./.venv
```

### 3. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run the Flask Application

```bash
python app.py
```

Open the application in your browser at:

```text
http://127.0.0.1:5000
```

### 5. Run Automated Tests

```bash
python -m pytest -v
```

### 6. Build the Docker Image

```bash
docker build -t flask-cicd-app .
```

### 7. Run the Docker Container

```bash
docker run -d -p 5000:5000 --name flask-container flask-cicd-app
```

Access the application at:

```text
http://localhost:5000
```

## GitHub Actions Automation

The CI/CD workflows are defined inside:

```text
.github/workflows/
```

The workflows automate application validation, testing, Docker image creation, and deployment.

The pipeline is designed to ensure that only successfully validated application changes proceed to the deployment stage.

## Security Practices

- Store deployment credentials and registry authentication tokens in GitHub Secrets.
- Never hardcode passwords, access tokens, or other sensitive credentials.
- Use minimum required GitHub Actions permissions.
- Exclude environment files and virtual environments from version control.
- Use appropriate Docker image tags and secure deployment practices.

## Learning Outcomes

Through this project, the following practical skills are developed:

- CI/CD pipeline design and implementation.
- GitHub Actions workflow configuration.
- Automated software testing.
- Docker image creation and container management.
- Continuous deployment automation.
- Environment and dependency management.
- Secure handling of deployment credentials.
- Debugging and troubleshooting automated workflows.

## Future Improvements

- Introduce Docker image vulnerability scanning.
- Implement Docker image tagging and version management.
- Add automated code quality checks using Ruff.
- Introduce multi-stage Docker builds.
- Add deployment health checks and rollback strategies.
- Integrate monitoring and logging.
- Extend the pipeline toward ML model testing and deployment.

## Author

**Haseeb Tariq**

BS Information Technology | Machine Learning & Software Engineering

GitHub: [@haseeb-ml-engineer](https://github.com/haseeb-ml-engineer)

---

*This project is developed for practical learning of DevOps principles, containerization, and automated software delivery using GitHub Actions.*