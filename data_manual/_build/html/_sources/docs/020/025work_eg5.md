# Sensirion SCD30 CO2 Sensors with HUZZAH32

This the sensor we are going to build in this exercise.

```{figure} /_static/025work_eg5/scd30_d1.jpg
:width: 100%
:name: scd_d1
```
We will need the following hardwares:
- HUZZAH32 (Can be bought [here](https://www.adafruit.com/product/3591))
- USB Data Cable
- A SCD30 Sensor (Can be bought [here](https://www.digikey.com/en/products/detail/sensirion-ag/SCD30/8445334))
- Jumper Wires x 4 (Can be bought [here](https://www.adafruit.com/product/1956))
- Breadboard (Can be bought [here](https://www.amazon.com/dp/B07DL13RZH/ref=redir_mobile_desktop?_encoding=UTF8&aaxitk=Ha8lI6PHb2sFCtkeyNViLQ&hsa_cr_id=4991273630901&pd_rd_plhdr=t&pd_rd_r=e429b428-9c18-43cc-bdb2-24937613797e&pd_rd_w=SmgRr&pd_rd_wg=zw5Ku&ref_=sbx_be_s_sparkle_mcd_asin_0_img))
- Soldering Kit (Can be bought [here](https://www.amazon.com/Soldering-Iron-Kit-Temperature-Desoldering/dp/B073VDX4B7/ref=sr_1_1_sspa?crid=3TI8MUBYG9QXZ&dchild=1&keywords=soldering+kit&qid=1615313665&s=industrial&sprefix=soldering%2Cindustrial%2C166&sr=1-1-spons&psc=1&smid=A1XLBTH0MIQMMO&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFHUTdTSUtLUkdESUQmZW5jcnlwdGVkSWQ9QTAzODE3MjcyS0REVDQ5U1JLSVk4JmVuY3J5cHRlZEFkSWQ9QTAxMjYzMDYxOTk2N0ZMSjdVUVI2JndpZGdldE5hbWU9c3BfYXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ==))
- Laptop

1. Solder the header to your SCD30. Follow similar soldering instructions [here](https://learn.adafruit.com/adafruit-sht31-d-temperature-and-humidity-sensor-breakout/assembly).
</Br><Br/>

2. Connect the HUZZAH32 and SCD30 onto the breadboard as shown in the previous figure. Wire up the Argon and the sensor as follows:
    </Br><Br/>
    a.  Connect the USB pin of the HUZZAH32 to VIN of the SCD30 sensor.
    ```{figure} /_static/025work_eg5/scd30_d2.jpg
    :width: 100%
    :name: scd30_d2
    ```

    b. Connect the Ground (GND) pin of HUZZAH32 to GND of SCD30 sensor.
    ```{figure} /_static/025work_eg5/scd30_d3.jpg
    :width: 100%
    :name: scd30_d3
    ```

    c. Connect the HUZZAH32 SCL pin to SCL of the SCD30 sensor.
    ```{figure} /_static/025work_eg5/scd30_d4.jpg
    :width: 100%
    :name: scd30_d4
    ```

    d. Connect the HUZZAH32 SDA pin to SDA of the SCD30 sensor.
    ```{figure} /_static/025work_eg5/scd30_d5.jpg
    :width: 100%
    :name: scd30_d5
    ```
4. Refer to  **Step 4 to 15** of {doc}`021work_eg1` to register the Argon Device with the FROST-Server. For **Step 11a** use the following parameters to register the device. For **Step 12** flash the ‘STAPI_Sensirion_SCD30’ script to the device. Fill in the parameters with the datastream ID from the registered device.


## Securing Passwords and codes

1. Highest level of security, enable secure boot and flash encrpytion. Precompile and Freeze the python module and bundle it with the firmware. Require the most amount of effort with compiling and freezing modules.

    https://forum.micropython.org/viewtopic.php?t=4510

    https://limitedresults.com/2019/11/pwn-the-esp32-forever-flash-encryption-and-sec-boot-keys-extraction/

    https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/windows-setup.html

    https://iotworkers.com/board-development/esp32-the-secure-boot.html

    https://docs.espressif.com/projects/esp-idf/en/latest/esp32/security/secure-boot-v1.html#secure-boot-reflashable

    ### For Pycom boards
    Can use these instructions for references
    https://docs.pycom.io/advance/frozen/
    https://docs.pycom.io/advance/encryption/

2. Quite secure, but it will be very inconvenient as once the chip lose power, you will have to have physical access to the chip to restart. Store the password in memory. Once the board is restarted, all passwords are lost. https://forum.micropython.org/viewtopic.php?t=7013

    ```
    import machine
    rtc = machine.RTC()
    rtc.memory(b'hello')
    ```

3. Easiest and most convenient, but least secure. Encrpyt the password "https://forum.micropython.org/viewtopic.php?f=16&t=6726&p=38315&hilit=ucryptolib.aes#p38315" and compile it into .mpy file. The password will be encrypted into bytecode. The password won't be human readable. However, it is possible to reverse engineer the .mpy files and obtain the password.

    ```
    Download mpy-cross with

    $ pip install mpy-cross

    $ python -m mpy_cross F:\kianwee_work\spyder_workspace\upycraft\workSpace\scd30\main.py -march=xtensawin -X emit=bytecode

    $ ampy -p COM4 put F:\kianwee_work\spyder_workspace\upycraft\workSpace\scd30\connect_wifi.mpy
    ```
4. Using wifimanager library.

    ```
    https://randomnerdtutorials.com/micropython-wi-fi-manager-esp32-esp8266/
    ```
