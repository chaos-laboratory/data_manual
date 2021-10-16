# Restore data to InfluxDB 1.8

1. Restore the database to a new influxdb with eithor of these commands.
    ```
    $ influxd restore -online -db <db name> <path-to-backup>

    $ restore -online -db <path-to-backup>

    -online is for legacy data we can use -portable for more current InfluxDB

    $influxd restore -portable <path-to-backy-files>

    Example
    to restore specific database
    $ influxd restore -portable -db everything /influx_backup/everything

    to restore all databases
    $ influxd restore -portable /influx_backup/everything

    ```
