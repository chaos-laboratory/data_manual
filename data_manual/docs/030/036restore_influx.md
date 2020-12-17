# Restore data to InfluxDB 1.8

1. Restore the database to a new influxdb with eithor of these commands.
    ```
    $ influxd restore -online -db <db name> <path-to-backup>

    $ restore -online -db <path-to-backup>

    Example
    $ influxd restore -online -db everything /influx_backup/everything
    ```
