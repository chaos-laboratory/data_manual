# Install Docker on OIT Server
1. You will need to first add the necessary repository to the server. Talk to the OIT in charge to help you add new repository to the server.

## Alternative you can install Docker with the packages
1. Check the distribution of the server. I have check it, it is running Oracle Linux Server 7.9. The closest distribution to it is the CentOS distribution. As a result, we will use the rpm packages for CentOS 7 Server.
    ```
    $ cat /etc/os-release
    ```

2. Download the rpm packages [here](https://download.docker.com/linux/centos/7/x86_64/stable/Packages/). Choose the latest stable distribution. You will need to download 4 packages.
    ```
    docker-ce-cli
    containerd.io
    docker-ce-rootless-extras
    docker-ce
    ```

2. Once downloaded you can copy the rpm packages from your local machine to the OIT server with this command.
    ```
    scp C:\users\userX\Download\x.rpm userid@andlchaos300l.princeton.edu:.
    ```

3. You will need to install two extra dependencies [from](https://pkgs.org/). Search for these two packages and then again copy them to the server.
    ```
    fuse3-libs
    fuse-overlayfs 0.7
    slirp4netns 0.4
    ```

4. Then install the 4 packages in this sequence.
    ```
    1. yum install docker-ce-cli
    2. yum install containerd.io
    3. yum install docker-ce-rootless-extras docker-ce
    ```

5. Once everyhting is install. Run Docker service with this command.
    ```
    systemctl start docker
    ```
