# Installing Node.js

*Node.js is a cross-platform Javascript runtime environment used for running javascript outside web browser.*

## Installation

### Installing Node Version Manager (`nvm`)

1. For managing different node version, we'll use Node Version Manager for installing `node.js`.
2. Use the below command to install `nvm`.
    
    ```powershell
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.4/install.sh | bash
    ```
3. Verify the installation.
   
    ```powershell
    nvm --version
    ```
4. After finishing the setup wizard, you have `nvm` on your ubuntu system.

### Installing Node.js and `npm`

1. Open your powershell now, and run the following command for installing latest long-term support version of `node.js`.
```powershell
nvm install --lts
```
2. After this, execute the below command to use the above node version.
```powershell
nvm use 24.13.0
```
3. Verify node installation using the below command. This command should also work in Git Bash.
```powershell
node -v
```
4. For `npm` verification, run the following command.
```powershell
npm -v
```
5. If `npm` script is prevented from being executed, this is majorly because of security reasons. Powershell prevents locally installed scripts like `npm` from being executed due to security reasons.
6. Run the powershell as administrator and execute the below command to update the execution policy.
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```
7. Press `Y` to update the policy. Restart powershell and verify `npm` installation using the below command. It should work now.
```powershell
npm -v
```
