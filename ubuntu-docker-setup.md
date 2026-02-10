# Docker setup for Ubuntu

*Docker is a tool for running containerised applications.*

## Clean up previous Installations

1. If you ever installed some old version of docker, we need to clean up those files to avoid conflicts.

```bash
dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc podman-docker containerd runc

