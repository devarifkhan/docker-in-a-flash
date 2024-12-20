# Setting Up Docker on Ubuntu

Follow these steps to install and set up Docker on your Ubuntu system:

## Step 1: Update Your System
First, update your existing list of packages:
```bash
sudo apt update
```

## Step 2: Install Prerequisites
Install the necessary packages to allow apt to use a repository over HTTPS:
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

## Step 3: Add Docker’s Official GPG Key
Add Docker’s official GPG key to your system:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

## Step 4: Add Docker Repository
Add the Docker repository to APT sources:
```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Step 5: Update Package Database
Update the package database with the Docker packages from the newly added repo:
```bash
sudo apt update
```

## Step 6: Install Docker
Make sure you are installing from the Docker repo instead of the default Ubuntu repo:
```bash
sudo apt install docker-ce
```

## Step 7: Verify Docker Installation
Check if Docker is installed correctly by running:
```bash
sudo systemctl status docker
```

## Step 8: Run Docker Without Sudo (Optional)
If you want to run Docker commands without `sudo`, add your user to the Docker group:
```bash
sudo usermod -aG docker ${USER}
```
Log out and log back in so that the group membership is re-evaluated.

## Step 9: Test Docker Installation
Run the hello-world image to verify that Docker is installed correctly:
```bash
docker run hello-world
```

You have now successfully installed Docker on your Ubuntu system.