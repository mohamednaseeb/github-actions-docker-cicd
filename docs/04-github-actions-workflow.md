# GitHub Actions Workflow

## Overview

GitHub Actions was used to automate the CI process for this project.

The workflow automatically runs whenever code is pushed to the main branch of the GitHub repository.

---

## Workflow File Location

The workflow file is located at:

```text
.github/workflows/docker-build.yml
```

---

## Purpose of the Workflow

The purpose of this workflow is to:

* Detect code changes pushed to GitHub
* Start an automated CI pipeline
* Check out the repository code
* Build the Docker image
* Confirm that the application can be containerized successfully

---

## Trigger

The workflow is triggered by a push to the main branch.

```yaml
on:
  push:
    branches:
      - main
```

This means every time code is pushed to the main branch, GitHub Actions automatically starts the pipeline.

---

## Runner

The workflow runs on a GitHub-hosted Ubuntu runner.

```yaml
runs-on: ubuntu-latest
```

This creates a temporary Ubuntu environment where the pipeline commands are executed.

---

## Checkout Step

```yaml
- uses: actions/checkout@v4
```

This step downloads the repository code into the GitHub Actions runner.

Without this step, the workflow would not have access to the Dockerfile or application files.

---

## Docker Build Step

```yaml
- name: Build Docker Image
  run: docker build -t github-actions-docker-cicd .
```

This step builds the Docker image using the Dockerfile in the repository.

If the Dockerfile has errors, this step fails and the pipeline shows a failed status.

---

## CI Pipeline Flow

```text
Git Push
   |
   v
GitHub Repository
   |
   v
GitHub Actions Runner
   |
   v
Checkout Code
   |
   v
Build Docker Image
   |
   v
Success or Failure
```

---

## What Happens After Workflow Completion

If the workflow succeeds:

* GitHub shows a green check mark.
* The Docker image build was successful.
* The application passed the CI validation step.

If the workflow fails:

* GitHub shows a red failure mark.
* The logs can be checked to identify the issue.

---

## Important Note

This workflow currently performs Continuous Integration.

It builds and validates the Docker image automatically.

It does not automatically deploy the application to a server yet.

Automatic deployment will be implemented in a future Continuous Deployment project.

---

## Result

The GitHub Actions workflow successfully ran after code was pushed to the repository.

The Docker image was built automatically, confirming that the CI pipeline was working correctly.
