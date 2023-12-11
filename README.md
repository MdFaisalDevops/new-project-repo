# Hello World Docker Image CI/CD with GitHub Actions and AWS ECR

This repository demonstrates a simple CI/CD setup using GitHub Actions to build a Docker image for a Hello World application and push it to AWS Elastic Container Registry (ECR).

## Prerequisites

Before replicating this setup, ensure you have the following:

- An AWS account with the necessary permissions to create and manage ECR repositories.
- AWS Access Key ID and Secret Access Key stored as GitHub Secrets (named `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`).
- The ECR repository URL stored as a GitHub Secret (named `AWS_ECR_REGISTRY_URL`).
- Docker installed locally.

## Workflow Overview

The GitHub Actions workflow defined in `.github/workflows/docker-ecr.yml` does the following:

1. **Build Docker Image:**
   - Uses Docker Buildx to build a multi-stage Docker image.
   - Utilizes caching for faster builds.

2. **Push Docker Image to AWS ECR:**
   - Authenticates with AWS ECR using the provided credentials stored as secrets.
   - Pushes the Docker image to the specified ECR repository.

## How to Replicate

1. **Fork this Repository:**
   - Fork this repository to your own GitHub account.

2. **Configure GitHub Secrets:**
   - In your forked repository, go to `Settings` -> `Secrets`.
   - Add the following secrets:
     - `AWS_ACCESS_KEY_ID`: Your AWS Access Key ID.
     - `AWS_SECRET_ACCESS_KEY`: Your AWS Secret Access Key.
     - `AWS_ECR_REGISTRY_URL`: The URL of your AWS ECR registry.

3. **Trigger GitHub Actions Workflow:**
   - Make any changes to the repository or trigger a new commit.
   - Observe the GitHub Actions workflow running under the `Actions` tab.

4. **View Workflow Logs:**
   - Click on the workflow run to view detailed logs and see the progress of each step.

## Additional Notes

- This is a simple example, and you may need to customize the Dockerfile or workflow to fit your application's requirements.
- Make sure to adapt the AWS ECR repository name and Dockerfile according to your project.

Feel free to customize this setup based on your specific needs. If you encounter any issues, refer to GitHub Actions logs and AWS ECR documentation for troubleshooting.

Happy coding!
