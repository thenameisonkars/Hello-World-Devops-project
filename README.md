# Hello-World-Devops-project

This project demonstrates a simple "Hello World" application using Flask, Dockerized for easy deployment. It also includes a CI/CD pipeline using GitHub Actions for automatic building and deployment.

## Project Structure

- `app.py`: A simple Flask application that returns "Hello, World!".
- `Dockerfile`: Docker configuration for building the application image.
- `.github/workflows/docker-image.yml`: GitHub Actions workflow for building and deploying the Docker image.

## Getting Started

### Prerequisites

- Docker installed on your local machine
- Docker Hub account for storing the Docker image
- AWS EC2 instance with Docker installed for deployment

### Local Development

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/hello-world-app.git
    cd hello-world-app
    ```

2. Build the Docker image locally:

    ```bash
    docker build -t hello-world-app .
    ```

3. Run the Docker container locally:

    ```bash
    docker run -d -p 5000:5000 hello-world-app
    ```

4. Access the application at `http://localhost:5000`.

### CI/CD Pipeline

The project uses GitHub Actions for continuous integration and deployment. The pipeline does the following:

1. **Builds** the Docker image.
2. **Pushes** the Docker image to Docker Hub.
3. **Deploys** the Docker image to an AWS EC2 instance.

### GitHub Actions Workflow

The GitHub Actions workflow is defined in `.github/workflows/docker-image.yml`. Ensure you have the following secrets configured in your GitHub repository:

- `DOCKER_USERNAME`: Your Docker Hub username.
- `DOCKER_PASSWORD`: Your Docker Hub password.
- `EC2_HOST`: The public DNS or IP address of your EC2 instance.
- `EC2_SSH_KEY`: Your private SSH key for the EC2 instance.

## Deployment

The pipeline will automatically deploy the application to your EC2 instance on each push to the `master` branch.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
