# Move Docker Data Folder to /app Folder

This task is based on instructions [here](https://www.guguweb.com/2019/02/07/how-to-move-docker-data-directory-to-another-location-on-ubuntu/). We need more space as the /var directory only has 5gb of space. Make sure you have log in as root as shown here {doc}`031connect_oit`

1. Go to the directory /etc/docker and create a file name daemon.json.
    ```
    $ cd /etc/docker
    $ touch daemon.json
    ```

2. With vim open the file and write the following.
    ```
    {
      "data-root": "/app/docker"
    }
    ```

3. Create the directory with this command.
    ```
    $ mkdir /app/docker
    ```

4. Sync the old docker data to this new directory.
    ```
    $ cp -r /var/lib/docker/ /app
    ```

5. Restart Docker.
    ```
    $ service docker restart
    ```
