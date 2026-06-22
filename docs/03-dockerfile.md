# Dockerfile Configuration

## Overview

The Dockerfile is used to create a custom Docker image for the application.

It defines:

* Base image
* Application files
* Exposed ports
* Container startup behavior

---

## Dockerfile Used

```dockerfile
FROM nginx:latest

COPY app/index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

---

## Instruction Breakdown

### FROM nginx:latest

Purpose:

* Downloads the latest Nginx image from Docker Hub.
* Serves as the base image for the application.

Why it is needed:

Without Nginx there would be no web server available to serve the HTML page.

---

### COPY app/index.html /usr/share/nginx/html/index.html

Purpose:

* Copies the application HTML page into the Nginx web root directory.

Why it is needed:

Without this instruction the container would display the default Nginx welcome page instead of the custom application.

---

### EXPOSE 80

Purpose:

* Documents that the container listens on port 80.

Why it is needed:

Allows the application to be accessed through port mappings.

Example:

```bash
docker run -p 8090:80 image-name
```

---

## Building the Image

Command:

```bash
docker build -t github-actions-docker-cicd .
```

Result:

A Docker image is created locally.

---

## Running the Container

Command:

```bash
docker run -d -p 8090:80 --name cicd-demo github-actions-docker-cicd
```

Result:

The application becomes accessible through:

```text
http://SERVER-IP:8090
```

---

## Verification

Command:

```bash
docker ps
```

Expected Output:

The container should be running and listening on port 8090.

---

## Outcome

The Dockerfile successfully packages the application into a reusable Docker image that can be built automatically through GitHub Actions.
