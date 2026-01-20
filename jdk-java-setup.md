# Java Development Toolkit Setup
### Version 25.0.1

* JDK is the software development toolkit for developing java applications. It consist of Java runtime Environment (JRE) and development tools like compiler (`javac`), debugger (`jdb`), packaging tool (`jar`) etc.*

1. Download open source JDK from [here](https://jdk.java.net/25/).
2. After downloading the JDK zip file, verify its checksum i.e the file is not tampered.
3. Open the sha256 link on the above download link for windows zip file and copy it.
4. Run the following command. The hash mentioned is copied from the above link.
```bash
echo "2bbae75bc31a848b7cb5f297270efb7bef9bba0deeec6a671625563dc090ad69 openjdk-25.0.1_windows-x64_bin.zip" | sha256sum
 -c
```
5. If the file is not tempered, you'll receive the following message.
```bash
openjdk-25.0.1_windows-x64_bin.zip: OK
```
6. Now extract the zip file to the location of your choice.
7. Add a new system variable in environment variable called `JAVA_HOME` and point it to the JDK root folder (`jdk-25.0.1`).
8. Update the Path variable in system variables to `%JAVA_HOME%\bin`.
9. Check if JDK is installed using the following command.
```bash
java --version
```
10. If correctly installed, you'll see the following output.
```bash
openjdk 25.0.1 2025-10-21
OpenJDK Runtime Environment (build 25.0.1+8-27)
OpenJDK 64-Bit Server VM (build 25.0.1+8-27, mixed mode, sharing)
```
