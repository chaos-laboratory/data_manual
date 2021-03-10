# Register Sensor and ObservedProperties to Our Database

There are many ways to post to our database as long as you can make a Post REST API request. In this document we will show two ways. 1) Using the Particle Web IDE, 2) Using Python Scripting.

## Particle Web IDE
In this task we will use the Particle Web IDE to post a new sensor and observation properties to our database.

1. Go to the Particle [Web IDE](build.particle.io) and login with our CHAOS Lab credentials. Approach our lab memeber for the logins. In the Web IDE, go to Code -> Search for STAPI -> STAPI04_RegisterSensor.
    ```{figure} /_static/041reg_sensor/reg_sensor.png
    :width: 100%
    :name: reg_sensor

    Register a new sensor with this script.
    ```
    a. In this example, we are registering a DHT22 sensor. Here are the parameters for registering the sensor.
    ```
    name = "DHT22"; //name of the sensor
    desc = "Temperature and Humidity Sensor"; //description of the sensor
    encodeType = "url";
    metadata = "https://www.digikey.com/en/products/detail/adafruit-industries-llc/385/5774230";
    ```
    b. Flash the code to the Particle Device. The event page of the Particle Device will show this message if successfully registered.
    ```{figure} /_static/041reg_sensor/reg_sensor2.png
    :width: 100%
    :name: reg_sensor2

    Successful registration of a sensor.
    ```
    c. Go to [https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Sensors](https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Sensors) to get the details of the sensor. Use Firefox for the best viewing result. Take not of the ID as that is what will be specified when posting data to the database.
    ```{figure} /_static/041reg_sensor/reg_sensor3.png
    :width: 100%
    :name: reg_sensor3

    Details of the registered sensor.
    ```

2. Similar to registering a new sensor. Registering a new ObservedProperties uses the script 'STAPI05-RegisterObservedProp'.
    ```{figure} /_static/041reg_sensor/reg_obsprop.png
    :width: 100%
    :name: reg_obsprop

    Register a new observation property with this script.
    ```
    a. In this example, we are registering the property absolute humidity. Here are the parameters for registering the property.
    ```
    name = "Absolute Humidity"; //name of the observed properties
    desc = " Absolute Humidity"; //description of the property
    definition = "https://en.wikipedia.org/wiki/Humidity"; //a url or wiki entry to define the property, your website cannot contain #
    ```
    b. Once filled, flash the code to the device. You will receive details of the registration on the event page.
    </Br><Br/>
    c. Go to [https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/ObservedProperties](https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/ObservedProperties) to get the details of the property. Use Firefox for the best viewing result. Take not of the ID as that is what will be specified when posting data to the database.
    ```{figure} /_static/041reg_sensor/reg_obsprop2.png
    :width: 100%
    :name: reg_obsprop2

    Details of the registered property.
    ```
