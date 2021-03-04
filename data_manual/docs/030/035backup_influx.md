# Instructions to Backup Influxdb 1.2 (installed on chaosbox)
1. Connect to Chaosbox {doc}`032chaosbox`.
2. Create a directory for the back up by making a directory.
    ```
    sudo mkdir /home/chaos/influx_backup
    ```

    a. Create a new folder for the metastore and each database. metastore, csvtest, everything, gpstest, iaq, internal, mrt, particles, siemens, test, weather

3. Backup the metastore. The InfluxDB’s metastore contains internal information about the status of the system, including user information, database/shard metadata, CQs, RPs, and subscriptions.
    ```
    $ sudo influxd backup /home/chaos/influx_backup/metastore
    ```

4. Backup each database with the following command
    ```
    $ sudo influxd backup -database <database name> <backup path>

    Example:
    $ sudo influxd backup -database everything /home/chaos/influx_backup/everything
    ```
5. Once you have backup all database zip the folder. Zip the backup folder by typing in the command.
    ```
    $ sudo zip -r ifbu_yyyymmdd.zip /home/chaos/influx_backup
    ```

6. Logout of Chaosbox. Use the scp command to download the zipfile.
    ```
    $ scp chaos@chaosbox.princeton.edu:/home/chaos/ifbu_20200713.zip C:\test\
    ```

7. Upload the zip file to the Chaos Research Google Drive “Chaos Research/influx_backup”

8. To backup all the databases in the InfluxDB
    ```
    $ sudo influxd backup -portable <backup_path>
    ```
