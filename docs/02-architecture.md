# Architecture

## Overview

This project uses a simple containerized architecture consisting of a web application, a Docker image, GitHub repository, and GitHub Actions workflow.

The workflow automatically builds the Docker image whenever code is pushed to the repository.

---

## Architecture Diagram

```text
Developer
    |
    v
Local Repository
    |
    v
GitHub Repository
    |
    v
GitHub Actions Workflow
    |
    v
Docker Image Build
    |
    v
Build Success / Failure
```

---

## Components

### 1. Application Source Code

Location:

```text
app/index.html
```

Purpose:

* Contains the web page content.
* Serves as the application being containerized.

---

### 2. Dockerfile

Location:

```text
Dockerfile
```

Purpose:

* Defines how the Docker image is built.
* Uses Nginx as the base image.
* Copies the application files into the container.
* Exposes port 80.

---

### 3. GitHub Repository

Purpose:

* Stores application source code.
* Stores Dockerfile.
* Stores GitHub Actions workflow.
* Acts as the source of truth for the project.

---

### 4. GitHub Actions Workflow

Location:

```text
.github/workflows/docker-build.yml
```

Purpose:

* Automatically runs after every push.
* Checks out repository code.
* Builds the Docker image.
* Reports success or failure.

---

### 5. Docker Image

Purpose:

* Packages the application and Nginx web server.
* Provides a portable deployment artifact.
* Ensures consistency across environments.

---

## Workflow Process

### Step 1

Developer modifies application code.

### Step 2

Changes are committed and pushed to GitHub.

### Step 3

GitHub detects the push event.

### Step 4

GitHub Actions automatically starts the workflow.

### Step 5

Docker image build process begins.

### Step 6

Build succeeds or fails.

### Step 7

Results are displayed in the GitHub Actions dashboard.

---

## Benefits of This Architecture

* Automated validation of code changes
* Fast feedback for developers
* Consistent Docker image creation
* Reduced manual work
* Foundation for future CD pipelines

---

## Outcome

The architecture successfully automates Docker image creation through GitHub Actions whenever code is pushed to the repository.
