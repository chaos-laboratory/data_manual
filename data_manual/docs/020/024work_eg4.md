# Sensirion SCD30 CO2 Sensors with Particle Argon

This the sensor we are going to build in this exercise.

```{figure} /_static/024work_eg4/scd30_d1.png
:width: 100%
:name: scd_d1

Completed SCD30 Sensor
```

We will need the following hardwares:
- A Particle Argon (Can be bought [here](https://store.particle.io/products/argon))
- USB Data Cable (Should come with your Particle Argon)
- A SCD30 Sensor (Can be bought [here](https://www.digikey.com/en/products/detail/sensirion-ag/SCD30/8445334))
- Jumper Wires x 4 (Can be bought [here](https://www.adafruit.com/product/1956))
- Breadboard (Can be bought [here](https://www.amazon.com/dp/B07DL13RZH/ref=redir_mobile_desktop?_encoding=UTF8&aaxitk=Ha8lI6PHb2sFCtkeyNViLQ&hsa_cr_id=4991273630901&pd_rd_plhdr=t&pd_rd_r=e429b428-9c18-43cc-bdb2-24937613797e&pd_rd_w=SmgRr&pd_rd_wg=zw5Ku&ref_=sbx_be_s_sparkle_mcd_asin_0_img))
- Soldering Kit (Can be bought [here](https://www.amazon.com/Soldering-Iron-Kit-Temperature-Desoldering/dp/B073VDX4B7/ref=sr_1_1_sspa?crid=3TI8MUBYG9QXZ&dchild=1&keywords=soldering+kit&qid=1615313665&s=industrial&sprefix=soldering%2Cindustrial%2C166&sr=1-1-spons&psc=1&smid=A1XLBTH0MIQMMO&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFHUTdTSUtLUkdESUQmZW5jcnlwdGVkSWQ9QTAzODE3MjcyS0REVDQ5U1JLSVk4JmVuY3J5cHRlZEFkSWQ9QTAxMjYzMDYxOTk2N0ZMSjdVUVI2JndpZGdldE5hbWU9c3BfYXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ==))
- Laptop and Smart phone

1. Connect the Antenna to the Argon as shown in the previous figure.
</Br><Br/>

2. Solder the header to your SCD30. Follow similar soldering instructions [here](https://learn.adafruit.com/adafruit-sht31-d-temperature-and-humidity-sensor-breakout/assembly).
</Br><Br/>

3. Connect the Argon and SCD30 onto the breadboard as shown in the previous figure. Wire up the Argon and the sensor as follows:
    </Br><Br/>
    a.  Connect the 3x3 pin of the Argon to VIN of the SCD30 sensor.
    ```{figure} /_static/024work_eg4/scd30_d2.png
    :width: 100%
    :name: scd30_d2

    3v3 to VIN pin.
    ```

    b. Connect the Ground (GND) pin of Argon to GND of SCD30 sensor.
    ```{figure} /_static/024work_eg4/scd30_d3.png
    :width: 100%
    :name: scd30_d3

    GND to GND pin.
    ```

    c. Connect the Argon SCL pin to SCL of the SCD30 sensor.
    ```{figure} /_static/024work_eg4/scd30_d4.png
    :width: 100%
    :name: scd30_d4

    SCL to SCL pin.
    ```

    d. Connect the Argon SDA pin to SDA of the SCD30 sensor.
    ```{figure} /_static/024work_eg4/scd30_d5.png
    :width: 100%
    :name: scd30_d5

    SDA to SDA.
    ```
4. Refer to  **Step 4 to 15** of {doc}`021work_eg1` to register the Argon Device with the FROST-Server. For **Step 11a** use the following parameters to register the device. For **Step 12** flash the ‘STAPI_Sensirion_SCD30’ script to the device. Fill in the parameters with the datastream ID from the registered device.
    ```
    Explanation of each parameter

    thingName = "ARG003" // the given name pasted on the device
    thingDesc = "CO2 Sensing" //describe the deployment
    pins = "I2C-SCD30" //describe the pins connection on the particle device
    foiName = "Somewhere"; // name of place the device is located
    foiDesc = "Somewhere"; //description of the place
    locType = "Point"; // a point location
    enType = "application/vnd.geo+json"; // geojson for describing the location of the sensor
    coordx = -0; //lon/x
    coordy = 0; //lat/y
    coordz = 0.0; //elv/z
    nDs = 3; // how many sensors are attached to this particle device that is streaming single number result
    dsSnrIds[nDs] = {6,6,6};
    dsObsPropIds[nDs] = {5,1,3};
    String dsDescs[nDs] = {"co2", "air temp", "rel humidity"};
    String dsObsTypes[nDs] = {
                            "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement", "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement", "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement"}
    String dsUomNames[nDs] = {"parts per million", "degree celsius", "percentage"};
    String dsUomSyms[nDs] = {"ppm", "degC", "%"};
    String dsUomDefs[nDs] = {
                              "parts per million", "Degree Celsius", "percentage"
                            };
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
