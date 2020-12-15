# Access InfluxDB

## Install influxDB
You can either install influxDB following the instructions [here](https://portal.influxdata.com/downloads/) or run it with Docker. Install Docker following these [instructions](https://docs.docker.com/engine/install/debian/).


    $ sudo docker run -d --name influxdb influxdb:1.8.3


You can then get into the container to access InfluxDB by using this command.


    $ sudo docker exec -it influxdb bash

1. Type “influx” to be connected to the influxDB shell.
2. In an influxdb data are structured hierarchically as [such](https://docs.influxdata.com/influxdb/v1.7/concepts/key_concepts/).

    a. Databases

    b. Measurements – equivalent to a table in sql

    c. Time – every data has a time stamp

    d. Field keys and values – these are the data collected from your sensors

    e. Tag keys and values – these are metadata of each data, these are indexed so it is faster
     to query with tag keys and values

3. Next let’s try to explore the data in chaosbox. To see all the databases in the influxdb.
    ```
    show databases
    ```

4. To enter into a specific database, type in this command.
    ```
    use <name of database>
    ```
5. To see all measurements. Type in this command.
    ```
    show measurements
    ```
6. As an example, to look at the field keys from the “chaos” measurement, type in this command. There are only one field key called value and it is a float.
    ```
    show field keys from chaos
    ```
7. As an example, to look at the tag keys from the “chaos” measurement, type this command. There are 6 tag keys in the chaos measurement.
    ```
    show tag keys from chaos
    ```

8. As an example, to look at the series from “chaos” measurement, type in this command. You will be able to see all the series in the chaos measurement.
    ```
    show series from chaos
    ```
9. Now we will look at how to use the “select” statement to filter through the data to look at data of our interest.Type in the command below. As seen previously, the chaos measurement only has field key value. Limit 5 tells influxdb to only show the first 5 data.
    ```
    select value from chaos limit 5
    ```
10. As you can see the time is in timestamp format, to change the timestamp to datetime format, type in this command.
    ```
    precision rfc3339
    ```

11. This is not very informative, now we will look at the all the field and tags of a row of data. Type in the command below. Now we can see each row of data with all its tags.
    ```
    select * from chaos limit 5
    ```
12. We will now look at all the data that has location = ‘ColdTube’. Type in the command below.
    ```
    select * from chaos where location='ColdTube' limit 10”
    ```
13. Now let’s filter the data with two where AND statement. Type in the following command.
    ```
    select * from chaos where location = 'ColdTube' and event = 'humid' limit 10
    ```
14. Let’s filter the data with the OR statement. Type in this command.
    ```
    select * from chaos where event = 'temp' or event = 'humid' limit 10
    ```
15. Let’s select according to time. Type in the following command.
    ```
    select * from chaos where location = 'ColdTube' and time >= '2019-01-01T00:00:00Z' and time <= '2019-02-01T00:00:00Z' limit 10
    ```
16. Now let’s count how many data there are that has location=’ColdTube’. Type in this command. There are close to 16 million data.
    ```
    select count(*) from chaos where location = 'ColdTube' and time >= '2019-01-01T00:00:00Z' and time <= '2019-02-01T00:00:00Z'
    ```
17. Now let’s export these data into a csv file. As it is not possible to export all the data, we will only export part of the data. The data will be exported locally to the chaosbox server. Type in this command.
    ```
    influx –precision ‘rfc3339’ -database 'everything' -execute "select * from chaos where location = 'ColdTube' or location = 'ColdTume' and time >= '2019-01-08T00:00:00Z' and time >= '2019-01-09T00:00:00Z'" -format 'csv' > coldtube_jan8_9.csv
    ```
18. Exit Influx and Chaosbox. Type in the command below to save the file into a folder call test in the c drive of your local machine. Once downloaded you have access to the csv file.
    ```
    scp chaos@chaosbox.princeton.edu:/home/chaos/coldtube_jan8_9.csv C:\test\
    ```
