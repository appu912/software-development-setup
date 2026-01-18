# Installing Git Bash for Windows

## A version control system.

1. Download Git Bash for Windows from [here](https://git-scm.com/install/windows).

2. Download Windows Terminal from Microsoft store.

3. Run the Git exe installer.

4. Set the location where you want to install Git.

5. Tick the option "Add Git Bash Profile to windows terminal". This will enable you to open Git Bash Terminal in Windows Terminal.

6. Tick the "Bundled OpenSSH" provided by Git. This will provide OpenSSH with no dependency on windows configuration.

7. Tick the "Use OpenSSL Library" which will match Linux/macOS Git behaviour.

8. Tick the "Checkout Windows-style, commit Unix-style" option. This will checkout with CRLF (\\r\\n like Windows editor) and commit with LF (\\n like Linux editor).

9. Choose MinTTY as your terminal editor.

10. Choose the "Fast Forward and merge" option for git pull behaviour. This will enable the following operations:
    - Fast Forward: If no local commits are there.
    - Merge: If both local and remote branch have commits.

11. Use the Git Credential Manager since it will store the credentials in Windows Credential Manager.

12. Also enable File Caching to save file status. This will optimize file scanning commands like git status.



After Installation

1\. Open windows terminal and create a new profile.

2\. Provide a name to your profile.

3\. For the Command Line field, enter the path to your bash.exe file. The default installation path is "C:\\Program Files\\Git\\bin\\bash.exe".

4\. For the icon field, enter the path for your Git Bash icon. You can use "C:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico".

5\. Update your starting directory to %USER\_PROFILE%.



Basic setup

1\. git config --global user.name "Your Name"

2\. git config --global user.email "example@gmail.com"

3\. Now enable encrypted connection between your local machine and GitHub using SSH.

4\. First check if you already have SSH key on your system or not using the following command: ls -al ~/.ssh

5\. If there is no .ssh file or the file is empty, then you don't have any ssh keys.

6\. Now we'll generate a new SSH key using the following command: ssh-keygen -t ed25519 -C "your\_email@example.com"

7\. Now add the ssh private key to your ssh-agent. For that we use powershell with admin rights and start the ssh-agent.

Get-Service -Name ssh-agent | Set-Service -StartupType Manual

Start-Service ssh-agent

8\. Then we'll add the ssh key to the ssh-agent: ssh-add c:/Users/YOU/.ssh/id\_ed25519

9\. Now we'll add ssh public key to the GitHub account. Follow this url: https://docs.github.com/en/enterprise-cloud@latest/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

10\. After this we can check the authenticity of the GitHub host using the following command: ssh -T git@github.com

11\. If the host is not verified, press yes if the generated fingerprint is present in the list present in the following url: https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints

