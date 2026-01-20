# Installing Node.js

*Node.js is a cross-platform Javascript runtime environment used for running javascript outside web browser.*

## Installation

### Installing Node Version Manager (`nvm`)

1. For managing different node version, we'll use Node Version Manager for installing `node.js`.
2. Node Version Manager was created for Linux/MacOS but we can use [this](https://github.com/coreybutler/nvm-windows/releases) to install it on windows environment.
3. Due to this `nvm` command will be accessible from powershell and not Git Bash because it does not have `sh` script.
4. Download the latest `nvm-setup.exe` from Assets in the above url.
5. Run the installer and provide the `nvm` installation directory and `node.js` installation directory.
6. After finishing the setup wizard, you have `nvm` on your windows system.

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
