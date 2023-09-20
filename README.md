

# Flask "Hello World" Dockerized Application

This repository contains a simple Flask "Hello World" application that can be containerized using Docker. The Flask application is configured to read an environment variable to greet users.

## Prerequisites

- Python 3.9+
- Docker

## Flask Application

The Flask application (`app.py`) serves a greeting message. By default, it will greet "World", but you can customize the greeting message using the `GREETING` environment variable.

## Docker

A `Dockerfile` is provided to containerize the application.

### Building the Docker Image

To build the Docker image, navigate to the directory containing the `Dockerfile` and run:

```bash
docker build -t flask-hello-world .
```

This command builds the Docker image and tags it as `flask-hello-world`.

### Running the Docker Container

To run the container and serve the Flask application:

```bash
docker run -p 5000:5000 -e GREETING='Docker World' flask-hello-world
```

The application will be accessible at `http://localhost:5000`.

## Pushing to Docker Hub

To push the image to Docker Hub, follow these steps:

1. **Login to Docker Hub**:
    ```bash
    docker login
    ```

2. **Tag Your Image**:

    Replace `myusername` with your Docker Hub username:

    ```bash
    docker tag flask-hello-world myusername/my-flask-app:latest
    ```

3. **Push the Image**:

    ```bash
    docker push myusername/my-flask-app:latest
    ```

4. Your image will now be available publicly on Docker Hub.

## Conclusion

This repository offers a quick way to containerize a simple Flask application and push it to Docker Hub. Always remember to avoid including any sensitive data in your Docker images and always follow best practices for Docker and Flask applications.
