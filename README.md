# KAMOTEQ-SWITCH
For Personal Use only | Not for Commercial

Tested on Arduino Uno | Esp8266 NodeMCU | Windows 8 and above

![alt text](https://github.com/kamoteqv2/kamoteq-repo/blob/main/lab-setup.jpg?raw=true)

## KamoteQ-switch Firmware Documentation
The Kamote-Q or KMQ firmware is a microcontroller board firmware that allows users to control the microcontroller output pins or read DHT sensor data from OpenHAB or Home Assistant applications.

### How to use the KamoteQ-switch firmware:
You must connect the microcontroller board to your PC or laptop before flashing the esp8266 nodeMCU or Arduino uno with Kamote-Q firmware. To verify the COM port number, use the device manager. You can install the driver by browsing in the repository's driver folder if the device is not correctly identified or the board's device driver is absent.

Once you have confirmed that the device is properly detected and the driver is installed, follow these steps:

1. Flash the firmware onto the board using the appropriate flasher software (XLoader for Arduino Uno, NodeMCU flasher for ESP8266).
2. Connect the board to your desired circuit or device. <click here for complete instruction>

## Integration with OpenHAB or Home Assistant:
### To use the KamoteQ-switch firmware with OpenHAB or Home Assistant, follow these steps:

1. Install OpenHAB or Home Assistant on your desired device.
2. Add the KamoteQ-switch firmware as a new thing in your smart home automation application.
3. Once the new board is added as a thing, you can control the pins and perform various actions on the board using the OpenHAB or Home Assistant user interface. <click here for complete instruction>
  
or check this online video tutorial https://www.youtube.com/watch?v=4bzahDY59fA

## Integration with Serial Commands:
### To use the KamoteQ-switch firmware with serial commands, follow these steps:

1. Connect the board to your desired circuit or device.
2. Open the Arduino IDE software and navigate to the "Tools" menu. Select the appropriate board and port settings.
3. Open the Serial Monitor by clicking on the magnifying glass icon on the top right corner of the IDE window.
4. Set the baud rate to 115200.
5. Type in the desired serial commands for the KamoteQ-switch firmware in the Serial Monitor input box and press "Enter".
6. The firmware will receive the command and perform the necessary actions.
  
Alternatively, if the Arduino serial monitor is not available, you can use the Termite serial monitor application, which is included in the repository. Once you have installed and run Termite, simply select the correct COM port number and set the baud rate to 115200. This will allow you to send and receive serial commands to the KamoteQ-switch firmware.


***Note:*** Refer to the available serial commands section for a list of commands you can use to control the board with serial commands.

### Available serial commands for Arduino:

#### Commands for erasing board information:  
- {"erasepins":1}: Sets all board pin statuses to the default "off" or "zero". In addition to using the serial command, board information can also be erased by placing a jumper wire between GPIO 13 and ground while the board is powered on.
  
#### Commands for controlling the board and updating settings:  
- {"pinNum": [pinNum],"setMod": [1|0]}: Sets a specific pin on the microcontroller board to the desired state. Replace the first value with the pin number you want to set, and the second value with the mode you want to set it to (e.g. "HIGH", "LOW").
- {"devicename":"mydevicename"}: Updates the device name to "mydevicename".
- {"rst":1}: This command resets the board.
#### Commands for getting board information:
- {"dht":1}: Retrieves values from the DHT sensor. 
- {"nfo":1}: Retrieves board values 
- {"pinNum": [pinNum],"getMod": 1}: This command inspect a specific pin on the board to display current state.   

***Note:*** There are a maximum of 16 output pins that can be used on the firmware for Arduino: D5-D19. Refer to the KamoteQ-switch firmware repository for the latest available commands and their descriptions.

### Available serial commands for ESP8266:

#### Commands for controlling the board and updating settings:
- {"rst":1}: This command resets the ESP8266 board.
- {"pinNum": [pinNum],"setMod": [1|0]}: This command sets a specific pin on the board to the desired state. Replace with the pin number you want to set, and with the mode you want to set it to (e.g. "HIGH", "LOW").
- {"ssid":"mywifi","password":"mypass"}: Use this command to update the wifi settings with your network name and password.
- {"devicename":"mydevicename"}: Use this command to update the device name.

#### Commands for erasing board information:
- {"erase":1}: This command erases the board's pin and wifi settings.  In addition to using the serial command, board information can also be erased by placing a jumper wire between GPIO 13 and ground while the board is powered on.
- {"erasewifi":1}: This command erases the wifi settings.
- {"erasepins":1}: This command sets all pins to default 0.

#### Commands for getting board information:
- {"nfo":1}:  
- {"dht":1}: Use this command to get the DHT sensor values.  
- {"pinNum": [pinNum],"getMod": 1}: This command inspect a specific pin on the board to display current state.  
  
***Note:*** There are a maximum of 4 output pins that can be used on the firmware for ESP8266: GPIO 4, 5, 12, 14. Refer to the KamoteQ-switch firmware repository for the latest available commands and their descriptions.
  

## New Feature: Porttyapi.exe
A new application called ***Porttyapi.exe*** has been added to the KMQ Application Group. This application enables users to use the ESP8266 or Arduino Uno even when Wi-Fi or Ethernet Shield is not available> This application will use the computer network interface to exchange data with the OpenHAB webserver, and use the serial communication to exchange data between the porttyapi.exe and the microcontroller boards (Esp8266 | Arduino Uno)
  
  and instead of using Instead, it uses the serial port to connect to the device.

With ***Porttyapi.exe***, you can create things and items with your favorite ESP8266 or Arduino without connecting it to a Wi-Fi network or a Wi-Fi connection in OpenHAB or Home Assistant. This allows for more flexibility in using the KMQ device and expands the range of possible applications.

To use ***Porttyapi.exe***, simply connect your ESP8266 or Arduino Uno to the KMQ device using a serial cable. Then, run the Porttyapi.exe application and follow the on-screen instructions to set up your device. Once set up, you can use your ESP8266 or Arduino Uno with the KMQ device even when Wi-Fi is not available.

Please note that the ***Porttyapi.exe*** application is only compatible with ESP8266 and Arduino Uno devices. If you are using a different device, you will need to connect it to Wi-Fi in order to use it with the KMQ device. https://github.com/kamoteqv2/porttYapi

## Credit:

This application was developed by KMQ Tech TV (https://www.youtube.com/@kamoteqv2), a Youtube channel dedicated to teaching and promoting Free DIY technology.
