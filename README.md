# M5Stack Core2
 Cardano Price Ticker

Add M5Stack in Arduino IDE
Before we can start compiling, the Arduino IDE must have the M5Stack Core2 board, based on an ESP32 in the board selection available. The instruction on https://docs.m5stack.com/#/en/arduino/arduino_core2_development In board selector you can select "M5Stack Core2" for M5Stack Core2.

For MAC users install the "CP210x USB to UART Bridge VCP Drivers" from Silicon Labs, the port to select is /dev/cu.SLAB_USBtoUART in Arduino IDE under tools-->Port
https://www.silabs.com/community/interface/knowledge-base.entry.html/2017/01/10/legacy_os_softwarea-bgvU


Libraries for Arduino IDE
Now we add libraries for Arduino IDE 1.8.13:
The new api requires a developer key, so you must apply for a key to use https://pro.coinmarketcap.com/account
CoinMarketCapApi.h
ArduinoJSON version 6.x is testet
The genaral instruction for the "M5Stack Core2" can be found here https://docs.m5stack.com/#/en/core/core2
If you are have problem with the "wifi.h" delete the arduino/libraries/wiFi directory, you can use the esp32 WiFi.h


How to use
First start shows no Wifi or CMC key in the display. The first start open a Wifi AP, connect to this Wifi Price-Ticker_SETUP and open a web browser enter the following IP address "192.168.4.1". Please enter your data here, after submitting this data will be saved and it is not necessary to enter it again.
After the automatic restart, the price ticker connects to your wifi and shows your setting on the display, to check that everything is saved. If the price ticker is connected to the internet, it retrieves data from Coinmarketcap and shows it on the display, every 260sec. the data will be updated.

Cover



Reset stored config
There are two ways to reset the setting, first if no wifi connection is established, only the wifi setting is reset after 30sec., the CMC API key remains stored. second possibility, if the price ticker is connected to the wifi, the setting can be reset via the assigned ip address (in my case is this 192.168.1.227), and the CMC API key is also deleted. Then the price ticker starts again in Wifi AP mode.
Cover


Display lighting
The lower 3 soft touch buttons set the brightness of the street in 3 steps. Button A = low, button B = middle, button C = high
