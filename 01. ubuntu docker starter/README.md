# Docker Installation Guide

Follow these steps to install Docker on Ubuntu:

## Step 1: Update APT

```sh
sudo apt-get update
```

## Step 2: Install Required Packages

```sh
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

## Step 3: Add Docker GPG Key

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

## Step 4: Add Docker Repository

```sh
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Step 5: Update APT Again

```sh
sudo apt-get update
```

## Step 6: Install Docker Engine

```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

## Step 7: Add User to Docker Group

To run Docker commands without `sudo`, add your user to the Docker group:

```sh
sudo usermod -aG docker $USER
```

Log out and log back in so that your group membership is re-evaluated.

## Step 8: Pull Nginx Image

To verify that Docker is installed correctly, pull the Nginx image:

```sh
docker pull nginx
```

You can now run an Nginx container using:

```sh
docker run --name my-nginx -p 80:80 -d nginx
```

This will start an Nginx server accessible on port 80.
## Step 9: Stop and Remove Nginx Container

To stop the running Nginx container, use:

```sh
docker stop my-nginx
```

To remove the stopped Nginx container, use:

```sh
docker rm my-nginx
```

To remove the Nginx image, use:

```sh
docker rmi nginx
```