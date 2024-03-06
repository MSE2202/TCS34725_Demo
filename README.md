# TCS34725 Demo

This demo connects to a TCS34725 colour sensor over the I2C bus and allows the measured colour components to be observed using the Serial Monitor. If working properly, the RBGC values will vary when objects of different colours are placed in close proximity to the sensor. SW0 (S1-2) may be used to turn the illumination LEDs on the TCS34725 on and off.

## Hardware Required

For this demo, you will require the following components:

* MSEduino ESP32-S3 based development board
* TCS34725 colour sensor
* Jumper or Dupont wires (M–F) to connect components

![TCS34725 Demo Schematic](docs/TCS34725_schematic.png)

### Build and Flash

Open the [Arduino IDE](https://www.arduino.cc/en/software) and configure it for the ESP32. Use a USB-A extension cable to connect your MSEduino to your computer. Use the **Tools→Board→esp32** menu to select the **Adafruit Feather ESP32-S3 No PRAM board**. The Port should be set as **COMx** on Windows or **dev.cu.usbmodel14101** (or similar) on Mac. The code provided with this lab requires version 2.0.11 of the Arduino-ESP32 boards. Use the **Tools→Board→Boards Manager...** menu and find the **esp32 by Espressif** board package. Confirm that the version is **2.0.11**. If necessary, use the dropdown menu to change versions. The code will not work in versions 3.0+ due to changes made to the underlying esp-idf API.

#### VSCode and PlatformIO

Note that as an alternative to the Arduino IDE, this project can be developed using [VSCode](https://code.visualstudio.com) with the [PlatformIO IDE](https://platformio.org/platformio-ide) extension and the [Espressif 32 platform](https://registry.platformio.org/platforms/platformio/espressif32) installed.

### Library Installation

In order to compile properly, the code in this repository requires the following libraries to be installed:

#### Adafruit NeoPixel

The [Adafruit NeoPixel Library](https://github.com/adafruit/Adafruit_NeoPixel) is a third-party library that can be installed directly from the Arduino IDE Library Manager. Go to **Tools→Manage Libraries...**. Use the search box to find and install the AdaFruit NeoPixel library.

#### Adafruit TCS34725

The [Adafruit TCS34725 Library](https://www.arduino.cc/reference/en/libraries/adafruit-tcs34725/) is another third-party library that can be installed from the Ardinio IDE Library Manager. Go to **Tools→Manage Libraries**. Enter "tcs34725" in the filter textbox. Scroll to find the "**Adafruit TCS34725** by Adafruit" library. Ensure that the latest version (≥ 1.4.4) is selected and press the **INSTALL** button. You will be asked whether you also want to install the dependency **Adafruit BusIO**. Select **INSTALL ALL**. 

![Install Adafruit TCS34725 Library](docs/Install_TCS34725.png)

For users of VSCode/PlatformIO, dependancies for the Adafruit libraries are contained in the `platformio.ini` configuration file. These will automatically install the libraries, if necessary.

## Resources

* [Arduino Language Reference](https://www.arduino.cc/reference/en/)
* [TCS34725 Colour Sensor Datasheet](https://cdn-shop.adafruit.com/datasheets/TCS34725.pdf)
* [Adafruit TCS34735 Arduino Library](https://www.arduino.cc/reference/en/libraries/adafruit-tcs34725)
* [Adafruit TCS34725 GitHub](https://github.com/adafruit/Adafruit_TCS34725)
