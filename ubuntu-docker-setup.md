# Docker setup for Ubuntu

*Docker is a tool for running containerised applications.*

## Clean up previous Installations

1. If you ever installed some old version of docker, we need to clean up those files to avoid conflicts.
    
    ```bash
    sudo apt remove $(dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc podman-docker containerd runc | cut -f1)
    ```
2. The above command will check if the packages are installed or not and remove them safely from the system.

## Docker APT Repository Setup

### Downloading docker's official gpg key

1. Now we need to setup docker apt repository from where we can download docker. This will help us to update and install docker easily using apt.
2. First we'll update the apt repository.
    
    ```bash
    sudo apt update
    sudo apt upgrade
    ```
3. Now we'll install ca-certificates and curl for downloading docker's official GPG key.
    
    ```bash
    sudo apt install ca-certificates curl
    ```
4. Now we'll create a directory with `/etc/apt/keyrings` using the `install` command with the following permissions.
    - `0` - special bits (none)
    - `7` - owner: read + write + execute
    - `5` - group: read + execute
    - `5` - others: read + execute
    
    ```bash
    sudo install -m 0755 -d /etc/apt/keyrings
    ```
5. Now we'll download docker's public signing GPG key and store it in the `/etc/apt/keyrings/docker.asc`.
    - `-f` - fails silently on HTTP errors - If server returns 404, 403 etc, curl returns with no HTML page being written in your key file.
    - `-s` - silent mode - No progress bar
    - `-S` - show error - If `-s` is used, errors are still shown.
    - `-L` - follow redirects - Curl follow redirects automatically.
    
    ```bash
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    ```
6. Now we will add read permissions to docker gpg key to all the users.
    
    ```bash
    sudo chmod a+r /etc/apt/keyrings/docker.asc
    ```

### Adding the docker repository to apt sources

1. Now we'll add the docker repository to apt sources.
    
    ```bash
    sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
    Types: deb
    URIs: https://download.docker.com/linux/ubuntu
    Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
    Components: stable
    Signed-By: /etc/apt/keyrings/docker.asc
    EOF

    sudo apt update
    sudo apt upgrade
    ```

### Installing docker using apt repository

1. Install docker using the apt command.
  
    ```bash
    sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    ```
2. Check if docker is running on your system.
    
    ```bash
    sudo systemctl status docker
    ```
3. You'll see something like this.
    
    ```bash
    Active: active (running)
    ```
4. Verify the installation using the below command as well.
    ```bash
    docker --version
    ```
5. This will show you the docker version installed on your system.

## Post Installation

1. Please run the below command to see the containers.
    
    ```bash
    docker ps
    ```
2. If you see permission denial issues, then please follow the below steps.
3. You can run using sudo, but please don't. We'll add you `user` to the docker group.
4. Run the below, command.
    
    ```bash
    ls -l /var/run/docker.sock
    ```
5. You can see that the docker group has read/write permission to this docker.sock file.
6. Lets add the user to this docker group. First create the group (If it doesn't exists).
    
    ```bash
    sudo groupadd docker
    ```
7. Add the user to the group.
    
    ```bash
    sudo usermod -aG docker $USER
    ```
8. Execute the below command to activate the changes made to the group.
    
    ```bash
    newgrp docker
    ```
9. Finally you can execute the below command.
    
    ```bash
    docker ps
    ```
