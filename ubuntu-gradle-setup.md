# Gradle setup for Ubuntu

*Gradle is a build tool for fast, dependable and adaptable open-source build automation tool.*

## Installation

1. Before installing gradle, we need to have JVM or JDK installed on our machine to run `gradle`. We also need to setup `JAVA_HOME` environment variable.
2. First locate your JDK installation path.
    
    ```bash
    readlink -f $(which java)
    ```
3. This will give you the location of your installed JDK.
    
    ```bash
    /usr/lib/jvm/java-21-openjdk-amd64/bin/java
    ```
4. Open your `~/.bashrc` and create a `JAVA_HOME` variable.
    
    ```bash
    export JAVA_HOME="/usr/lib/jvm/java-21-openjdk-amd64"
    ```
5. To install the latest version of gradle, we'll use sdkman (It manages gradle versions).
6. Use the below command to install sdkman.
    
    ```bash
    curl -s "https://get.sdkman.io" | bash
    ```
7. After installing sdkman, we can use it to install gradle.
    
    ```bash
    sdk install gradle
    ```
