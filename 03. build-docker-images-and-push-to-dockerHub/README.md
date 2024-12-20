# Create and Push Docker Images to Docker Hub: A Step-by-Step Guide

## Prerequisites
- Docker installed on your machine
- Docker Hub account

## Step 1: Build the Docker Image
Navigate to the directory containing your Dockerfile and build the Docker image using the following command:

```sh
cd docker-in-a-flash/03. build-docker-images-and-push-to-dockerHub/Dockerfiles
docker build -t your_dockerhub_username/your_image_name:tag .
```

Replace `your_dockerhub_username`, `your_image_name`, and `tag` with your Docker Hub username, desired image name, and tag respectively.

## Step 2: Log in to Docker Hub
To push the image to Docker Hub, you need to log in first. Use the following command:

```sh
docker login
```

You will be prompted to enter your Docker Hub username and password. Alternatively, you can use a token for login.

### Using a Token for Login
1. Go to [Docker Hub](https://hub.docker.com/) and log in.
2. Navigate to **Account Settings** > **Security**.
3. Click on **New Access Token** and generate a token.
4. Use the token to log in:

```sh
docker login -u your_dockerhub_username --password-stdin
```

You will be prompted to enter the token.

## Step 3: Push the Docker Image to Docker Hub
After logging in, push the image to Docker Hub using the following command:

```sh
docker push your_dockerhub_username/your_image_name:tag
```

Replace `your_dockerhub_username`, `your_image_name`, and `tag` with the same values used in the build command.

## Conclusion
You have successfully built and pushed a Docker image to Docker Hub. You can now use this image in your projects or share it with others.
