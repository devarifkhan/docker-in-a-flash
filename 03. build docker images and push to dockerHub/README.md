# Create and Push Docker Images to Docker Hub: A Step-by-Step Guide

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

## Step 4: Run the Docker Image
To run the Docker image you just pushed with port mapping, use the following command:

```sh
docker run -d -p host_port:container_port your_dockerhub_username/your_image_name:tag
```

Replace `host_port` with the port on your host machine, `container_port` with the port inside the container, and `your_dockerhub_username`, `your_image_name`, and `tag` with the same values used in the build command.

## Step 5: Delete the Docker Image
If you need to delete the Docker image locally or from Docker Hub, use the following commands:

### Delete Locally
To delete the Docker image from your local machine, use:

```sh
docker rmi your_dockerhub_username/your_image_name:tag
```

### Delete from Docker Hub
To delete the Docker image from Docker Hub, log in to Docker Hub, navigate to your repository, and delete the image manually.

## Conclusion
You have successfully built, pushed, run, and deleted a Docker image from Docker Hub. You can now use this image in your projects or share it with others.
