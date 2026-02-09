# Installing Git on Ubuntu

## A version control system.
*Git is a version control system for tracking code changes.*

1. We can install Git using Advanced Package Tool (apt).
    
    ```bash
    sudo apt update
    sudo apt upgrade
    sudo apt install git
    ```
2. The above commands will install Git in system wide binaries (`/usr/bin/git`).
3. Verify the installation using the below command.
    
    ```bash
    git --version
    ```
4. The output of the above command will display the version of git.

## Basic setup

1. Execute the following commands:
    
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "example@gmail.com"
    ```
2. Now enable encrypted connection between your local machine and GitHub using SSH.
3. First check if you already have SSH key on your system or not using the following command: 
    
    ```bash
    ls -al ~/.ssh
    ```
4. If there is no .ssh file or the file is empty, then you don't have any ssh keys.
5. Now we'll generate a new SSH key using the following command: 
    
    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
6. Then we'll add the ssh key to the ssh-agent: 
    
    ```bash
    ssh-add ~/.ssh/id_ed25519
    ```
7. Now we'll add ssh public key to the GitHub account. Follow this [url](https://docs.github.com/en/enterprise-cloud@latest/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).
    
    ```bash
    pbcopy < ~/.ssh/id_ed25519.pub
    ```
8. After this we can check the authenticity of the GitHub host using the following command.
    
    ```bash
    ssh -T git@github.com
    ```
9. If the host is not verified, press yes if the generated fingerprint is present in the list present in the following [url](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints).
