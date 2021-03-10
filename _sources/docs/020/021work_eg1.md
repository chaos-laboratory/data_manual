# SHT31 Air Temperature & Humidity Sensor with Particle Argon

This the sensor we are going to build in this exercise.

```{figure} /_static/021work_eg1/sht31_6_labelled.jpg
:width: 100%
:name: sht31_6

Completed SHT31 Sensor
```

We will need the following hardwares:
- A Particle Argon (Can be bought [here](https://store.particle.io/products/argon))
- USB Data Cable (Should come with your Particle Argon)
- A SHT31 Sensor (Can be bought [here](https://www.adafruit.com/product/2857))
- Jumper Wires x 4 (Can be bought [here](https://www.adafruit.com/product/1956))
- Breadboard (Can be bought [here](https://www.amazon.com/dp/B07DL13RZH/ref=redir_mobile_desktop?_encoding=UTF8&aaxitk=Ha8lI6PHb2sFCtkeyNViLQ&hsa_cr_id=4991273630901&pd_rd_plhdr=t&pd_rd_r=e429b428-9c18-43cc-bdb2-24937613797e&pd_rd_w=SmgRr&pd_rd_wg=zw5Ku&ref_=sbx_be_s_sparkle_mcd_asin_0_img))
- Soldering Kit (Can be bought [here](https://www.amazon.com/Soldering-Iron-Kit-Temperature-Desoldering/dp/B073VDX4B7/ref=sr_1_1_sspa?crid=3TI8MUBYG9QXZ&dchild=1&keywords=soldering+kit&qid=1615313665&s=industrial&sprefix=soldering%2Cindustrial%2C166&sr=1-1-spons&psc=1&smid=A1XLBTH0MIQMMO&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFHUTdTSUtLUkdESUQmZW5jcnlwdGVkSWQ9QTAzODE3MjcyS0REVDQ5U1JLSVk4JmVuY3J5cHRlZEFkSWQ9QTAxMjYzMDYxOTk2N0ZMSjdVUVI2JndpZGdldE5hbWU9c3BfYXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ==))
- Laptop and Smart phone

1. Connect the Antenna to the Argon as shown in the previous figure.
</Br><Br/>

2. Solder the header to your SHT31. Follow the instructions [here](https://learn.adafruit.com/adafruit-sht31-d-temperature-and-humidity-sensor-breakout/assembly).
</Br><Br/>

3. Wire up the Argon and the sensor as follows:
    </Br><Br/>
    a. Connect the Argon and SHT31 onto the breadboard as shown in the previous figure. Connect the 3x3 pin of the Argon to the VIN pin of the SHT31 sensor.
    ```{figure} /_static/021work_eg1/sht31_2_labelled.jpg
    :width: 100%
    :name: sht31_2

    3x3 to VIN pin.
    ```
    b. Connect the Ground (GND) pin of Argon to the SHT31 sensor.
    ```{figure} /_static/021work_eg1/sht31_3_labelled.jpg
    :width: 100%
    :name: sht31_3

    GND to GND pin.
    ```
    c. Connect the Argon SCL pin to the SCL pin of the SHT31 sensor.
    ```{figure} /_static/021work_eg1/sht31_4_labelled.jpg
    :width: 100%
    :name: sht31_4

    SCL to SCL pin.
    ```
    d. Connect the Argon SDA pin to the SAA/RH pin of the SHT31 sensor.
    ```{figure} /_static/021work_eg1/sht31_5_labelled.jpg
    :width: 100%
    :name: sht31_5

    SDA to SAA/RH pin.
    ```

4. For use in Princeton Campus, please register your device with servicenet. Follow the instruction here {doc}`../030/040particle_servicenet`. You will need to register the smart phone you will use to register your particle device with the servicenet too.
</Br><Br/>
5. Register and setup your Particle device with our chaos lab particle account (You can do it with your own Particle account too). For login information to the Chaos account please approach members of the lab. Follow the instruction [here](https://setup.particle.io/).
    </Br><Br/>
    a. Sometimes, you might have some problem with registering. Doing a factory reset on the Argon might be useful. [Instructions to doing a factory reset](https://community.particle.io/t/how-to-do-a-factory-reset/2579). A summary is provided here.

    ```
    1) Begin holding the MODE button down.
    2) While holding the MODE button down, tap the RESET button briefly.
    3) After 3 seconds the core will begin blinking yellow, KEEP HOLDING the MODE button.
    4) After 10 seconds the core will begin blinking white.
    When this happens the factory reset process has begun. Let go of the MODE button.
    ```

6. Once your device is registered, go to the [particle web console](https://console.particle.io/devices). Check if the device is on the list.
    ```{figure} /_static/021work_eg1/particle_console.png
    :width: 100%
    :name: particle_console

    We have named our Argon HYDRO_ARG001.
    ```
7. Go to the [Web IDE](https://build.particle.io/build/new). Go to the Devices tab, star the device that you have registered.
    ```{figure} /_static/021work_eg1/web_ide.png
    :width: 100%
    :name: web_ide

    Star Argon HYDRO_ARG001, so we can flash to the device.
    ```
8. Click on the code option on the left side bar. In the search bar for 'My apps' search for 'STAPI'. You will see a series of STAPIXX_XXX scripts.
    ```{figure} /_static/021work_eg1/web_ide2.png
    :width: 100%
    :name: web_ide2

    STAPIxx series of scripts
    ```
9. For a general description of the integration of Particle with our database (FROST-Server) refer to [here](https://chenkianwee.github.io/masa3db/docs/040/042particle.html).

10. Flash the 'STAPI01_isDeviceRegistered' script to the Argon.
    ```{figure} /_static/021work_eg1/web_ide3.png
    :width: 100%
    :name: web_ide3

    Flash the STAPI01_isDeviceRegistered script to the device.
    ```
    a. If the device is not registered on our database you will see this message on My Devices->HYDRO_ARG001 event page.
    ```{figure} /_static/021work_eg1/web_ide4.png
    :width: 100%
    :name: web_ide4

    If the device is not registered on our database you will see this message.
    ```
    b. If the device is registered you will see this message on My Devices->HYDRO_ARG001 event page.
    ```{figure} /_static/021work_eg1/web_ide5.png
    :width: 100%
    :name: web_ide5

    If the device is registered on our database you will see this message.
    ```
11. We assumed the device is not registered on our database. If it is already registered, please refer to the register new deployment workflow ({doc}`../030/043new_deploy`). Flash the 'STAPI02_RegisterDevice' script. Fill in the parameters as shown in the figure below.
    ```{figure} /_static/021work_eg1/web_ide6.png
    :width: 100%
    :name: web_ide6

    Fill in the parameters to register the device on our database
    ```
    a. Fill in the parameters as follows. For more information on registering new Sensors and ObservedProperties please refer to the respective documents. Register New Sensor and ObservedProperties ({doc}`../030/041reg_sensor_obsprop`).
    ```
    Explanation of each parameter

    thingName = "HYDRO_ARG001" // the given name pasted on the device
    thingDesc = "Temperature and Humidity in Arch Lab" //describe the deployment
    pins = "I2C-SHT31_Temp Humidity" //describe the pins connection on the particle device
    foiName = "Arch Lab"; // name of place the device is located
    foiDesc = "Arch Lab for Hydroculus"; //description of the place
    locType = "Point"; // a point location
    enType = "application/vnd.geo+json"; // geojson for describing the location of the sensor
    //Define the location of the thing. If location is not impt, use [0,0,0] the null island position.
    coordx = -74.649916; //lon/x
    coordy = 40.343585; //lat/y
    coordz = 0.0; //elv/z

    //Define the datastream, a datastream is streaming measurements from a sensor
    each stream is associated with 1 sensor. There are two types of streams: datastreams and multidatstream
    1) datastream #measurement consists of only a number etc. temperature(C)
    2) multidatastream #measurement consist of two numbers etc. gps(lon, lat)

    nDs = 3; // how many sensors are attached to this particle device that is streaming single number result
    //Specify the Ids of the sensors that is attached to each datastream
    dsSnrIds[nDs] = {3,3,3}; // Visit http://chaosbox.princeton.edu:8080/FROST-Server/v1.0/Sensors to look at the sensor catalogue, if you can't find the sensors you need run STAPI04-RegisterSensors
    //Specify the Ids of the observation properties that is attached to each datastream
    dsObsPropIds[nDs] = {1,3,6};// Visit http://chaosbox.princeton.edu:8080/FROST-Server/v1.0/ObservedProperties to look at the observed properties catalogue, if you can't find the observed properties you need run STAPI05-RegisterObservedProperties
    //descriptions of the datastream
    String dsDescs[nDs] = {"air_temperature", "relative_humidity", "abs_humidity"};
    String dsObsTypes[nDs] = {
                            "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement", "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",
                            "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement"
                            }; // visit http://defs.opengis.net/elda-common/ogc-def/resource?uri=http://www.opengis.net/def/observationType/OGC-OM/2.0/&_format=html and choose one of the observation types
    //unit of measurement of the data
    String dsUomNames[nDs] = {"Degree Celsius", "Percentage", "g/kg"}; //name of unit of measurement e.g. temperature, daylight
    String dsUomSyms[nDs] = {"degC", "%", "g/m3"}; // the symbols of the unit of measurement e.g. C, lux
    String dsUomDefs[nDs] = {
                            "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#DegreeCelsius", "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#DegreeCelsius",
                            "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#DegreeCelsius"
                            }; //visit "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html" to get the definition

    //define multidatastreams #measurement consist of two numbers etc. gps(lon, lat)
    const int nMds = 0; // how many sensors are attached to this particle device that is streaming duo number result
    //Specify the Ids of the sensors that is attached to each multidatastream
    int mdsSnrIds[nMds] = {};
    //Specify the Ids of the observation properties that is attached to each datastream
    int mdsObsPropIds[nMds] = {};
    //descriptions of the datastream
    String mdsDescs[nMds] = {};
    String mdsObsTypes[nMds] = {};
    //unit of measurement of the data
    String mdsUomNames[nMds] = {};
    String mdsUomSyms[nMds] = {};
    String mdsUomDefs[nMds] = {};
    //elements in sensorIds, obsPropIds and dsOrMds must correspond.
    ```
    b. Once filled in flash the code to the device. Once the Device is successfully registered you will receive this message on the device events page. Take note of the datastream ids, we will need it for the next step. For this specific example we got 21,22,23 for the air temperature, relative humidity and absolute humidity respectively.
    ```{figure} /_static/021work_eg1/web_ide7.png
    :width: 100%
    :name: web_ide7

    Successful registration of the device
    ```
    c. We can also go to [https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Things](https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Things) to check if the device is registered. It is advice to use Firefox.
    ```{figure} /_static/021work_eg1/database1.png
    :width: 100%
    :name: database1

    Device registered on our database
    ```
12. Next we have to flash the 'STAPI_SHT31_1_Sensor' script to the device. Fill in the parameters with the datastream ID from the registered device. As mentioned our IDs are 21,22,23. You can also determine the interval of measurement. In this case, we have set it at every 10seconds. If you look at the script, you can see that it is posting measurement from the SHT31 to the respective datastreams (air temperature, relative humidity and absolute humidity).
    ```{figure} /_static/021work_eg1/web_ide8.png
    :width: 100%
    :name: web_ide8

    Post data to the database with 10 seconds interval
    ```
    a. Go to the device events page. You will see the device is posting data every 10s.
    ```{figure} /_static/021work_eg1/web_ide9.png
    :width: 100%
    :name: web_ide9

    Post data to the database with 10 seconds interval on the event page.
    ```

13. To check the data, go to [https://andlchaos300l.princeton.edu:3000](https://andlchaos300l.princeton.edu:3000), make sure you are logged into the Princeton VPN or on Princeton Campus. Login with our Chaos Lab Grafana Login. Approach out lab member for login details.

14. At the Grafana homepage, go to + sign at the sidebar. Create -> Dashboard -> Add New Panel. At the Query bar. Specify Things = HYDRO_ARG001, Datastream = 'HYDRO_ARG001_air_temperature'. You will be able to see the data. Set the refresh rate to very 5s. The visualised data might look alittle messy at first. But it will smoothen after a few hours. It is a bug with the sensorthings api plugin for Grafana. Repeat Add Panel for all the other datastream, 'HYDRO_ARG001_relative_humidity' and 'HYDRO_ARG001_absolute_humidity'
    ```{figure} /_static/021work_eg1/grafana.png
    :width: 100%
    :name: grafana

    Visualization of data in Grafana
    ```
15. To download the data as CSV from Grafana. Click on the Graph Title in our case is 'Air Temp' -> Inspect -> Data. You will be able to download the data to CSV. For more advance analytics, please refer to the Advance Analytics task {doc}`../030/042advance_analytics`.
    ```{figure} /_static/021work_eg1/grafana2.png
    :width: 100%
    :name: grafana2

    Downloading CSV from Grafana
    ```
