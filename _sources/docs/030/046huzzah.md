# Micropython on HUZZAH32

Overview of the <a href="https://learn.adafruit.com/adafruit-huzzah32-esp32-feather" target="_blank">HUZZAH32 board from Adafruit</a>. This exercise is based on a series of other tutorials available online. <a href="https://how2electronics.com/esp32-micropython-upycraft-getting-started/" target="_blank">Micropython with uPyCraft instructions</a>. <a href="https://github.com/pvanallen/esp32-getstarted" target="_blank">HUZZAH32 with Micropython getting started guide</a>. <a href="https://circuitdigest.com/microcontroller-projects/how-to-program-esp32-in-micropython-using-thonny-ide" target="_blank">Micropython with Thonny IDE</a>.

This exercise assumes you are familiar with programming with Python and Anaconda.

1. Download and install the driver necessary to read and write from HUZZAH32 <a href="https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers" target="_blank">here</a>. In this exercise, I am using a Windows machine. However, the steps should work for the other OSes.
    - Connect the HUZZAH32 board to your computer. Go to Device Manager. You should be able to see under Ports (COM & LPT) - Silicon Labs CP210x USB to UART Brigdge (COMx). Remember the COM number 'COM4' in my case.
    ```{figure} /_static/046huzzah/comport.PNG
    :width: 50%
    :name: comport
    ```
2. Download the <a href="https://micropython.org/resources/firmware/esp32-20210623-v1.16.bin" target="_blank">Micropython</a> firmware.

3. Install <a href="https://docs.conda.io/en/latest/miniconda.html" target="_blank">miniconda</a>. For instructions on how to use conda refer to <a href="https://docs.conda.io/projects/conda/en/latest/user-guide/index.html" target="_blank">this</a>.
    - Create an environment call micropython.
      ```
      $ conda create --name micropython python=3.9
      ```
    - Once created activate the environment and we will be working in this environment.
      ```
      $ conda activate micropython
      ```

4. Install the esptool.py tool with the following command in the micropython environment.
    ```
    $ pip install esptool
    ```

5. Type in this command to erase and flash the micropython onto the HUZZAH32 board. Remember the COM number of your HUZZAH32 board. Specify the directory of where you downloaded your Micropython firmware.
    ```
    $ esptool --chip esp32 --port COMx erase_flash
    $ esptool --chip esp32 --port COMx --baud 460800 write_flash -z 0x1000 <micropython_firmware>.bin
    ```
6. With Micropython install on your board. We can write some codes with the Thonny IDE. Download the Thonny IDE <a href="https://thonny.org/" target="_blank">here</a>.

7. In Thonny go to Tools -> Options -> Interpreter. In the 'Which interpreter or device should Thonny use for running your code?', choose Micropython (ESP32). In the 'Port or WebREPL', choose the COM your HUZZAH32 board is connected to.
    ```{figure} /_static/046huzzah/thonny.PNG
    :width: 100%
    :name: thonny
    ```
    - Once chosen, the shell will show it is connected to the Micropython on the HUZZAH32.
    ```{figure} /_static/046huzzah/thonny2.PNG
    :width: 100%
    :name: thonny2
    ```
8. Write a blink.py script and upload it onto the board to blink the LED on HUZZAH32. Go to File -> New. Copy and pase the codes onto the script.
    ```
    import machine
    import time

    #setup
    led = machine.Pin(13, machine.Pin.OUT) # LED on the board

    #loop
    while True:
      if led.value() == 0:
        led.value(1)
      else:
        led.value(0)
      time.sleep(0.5)
    ```
9. Go to File -> Save as ... -> Micropython device. Save the script as main.py.
    ```{figure} /_static/046huzzah/thonny3.PNG
    :width: 100%
    :name: thonny3
    ```
