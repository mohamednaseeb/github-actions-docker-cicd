# Project Overview

## Project Name

GitHub Actions Docker CI Pipeline

---

## Objective

The objective of this project was to build a basic CI pipeline using GitHub Actions and Docker.

The project demonstrates how a code change pushed to GitHub can automatically trigger a GitHub Actions workflow that builds a Docker image and verifies that the application can be containerized successfully.

---

## Technologies Used

* Ubuntu Linux
* Git
* GitHub
* GitHub Actions
* Docker
* Nginx
* HTML

---

## Project Description

A simple static web application was created using HTML.

The application was containerized using Docker with an Nginx base image.

A GitHub Actions workflow was configured to automatically run when code is pushed to the main branch.

The workflow performs the following tasks:

* Checks out the repository code
* Builds a Docker image
* Verifies that the Docker build completes successfully
* Confirms that the CI pipeline works automatically after code changes

---

## Application Structure

```text
github-actions-docker-cicd/
│
├── app/
│   └── index.html
│
├── Dockerfile
│
├── .github/
│   └── workflows/
│       └── docker-build.yml
│
├── docs/
│
└── screenshots/
```

---

## What This Project Demonstrates

This project demonstrates:

* Basic CI/CD concepts
* GitHub Actions workflow automation
* Docker image building
* Repository-based automation
* Code push triggering automated workflows
* Containerizing a simple web application

---

## CI Pipeline Flow

```text
Developer updates code
        |
        v
Git commit
        |
        v
Git push to GitHub
        |
        v
GitHub Actions workflow starts
        |
        v
Docker image is built
        |
        v
Pipeline succeeds or fails
```

---

## Important Note

This project currently demonstrates the CI part of CI/CD.

The pipeline automatically builds and verifies the Docker image when code is pushed to GitHub.

It does not yet automatically deploy the application to a production server.

Automatic deployment will be added in a future CD project.

---

## Outcome

The CI pipeline was successfully created and tested.

GitHub Actions automatically triggered after code changes and successfully completed the Docker build process.
