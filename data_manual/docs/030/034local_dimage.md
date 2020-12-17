# Downloading Docker Image Locally
1. Download Docker image with this command.
    ```
    $ sudo docker save fraunhoferiosb/frost-server:latest > frost-server.tar
    ```
2. Load the image with this command.
    ```
    $ sudo docker load -i frost-server.tar
    ```
