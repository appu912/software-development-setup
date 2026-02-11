# Java Development Toolkit Setup for Ubuntu

*JDK is the software development toolkit for developing java applications. It consist of Java runtime Environment (JRE) and development tools like compiler (`javac`), debugger (`jdb`), packaging tool (`jar`) etc.*

1. We can use the apt repository for installing JDK.
2. We can install JDK using the below commands.
   
    ```bash
    sudo apt update
    sudo apt upgrade
    sudo apt install openjdk-21-jdk
    ```
3. We can verify the installation using the below command.
    
    ```bash
    java --version
    ```
4. You can see that JDK is installed correctly.
    
    ```bash
    openjdk 21.0.10 2026-01-20
    OpenJDK Runtime Environment (build 21.0.10+7-Ubuntu-124.04)
    OpenJDK 64-Bit Server VM (build 21.0.10+7-Ubuntu-124.04, mixed mode, sharing)
    ```
