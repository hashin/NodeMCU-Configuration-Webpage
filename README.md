                                NodeMCU Configuration Server
MCU: ESP8266
Firmware: NodeMCU 0.9.5
Compiler: eLua 0.9.0 cross-compiler

Summary
-------

Wifi Access Point with HTTP Server to serve configuration page for new device 
in your wifi network. Made to be used as part of some bigger programs 
(example: NodeMCU-LavaLamp)


Usage
-----

run it in lua with:
    dofile('ap.lc')

After launching 'ap.lc' file program it will act as Access Point:
    SSID: 'Lava_Lamp_XXXXXXXX'
    PASS: 'lavalamp' 

When user connects to this network it will serve configuration web page at 
    http://192.168.1.1

This web page provides ESP8266 MAC address and asks for new network SSID and 
PASSWORD. After clicking "Submit" it starts countdown.
While user sees countdown, MCU switches to SOFTAP mode and tries to 
connect to new network while still acting as AP. If connection fails it sends 
user same page as earlier but with an error message addded. In case of success 
it should save configuration to 'wifi.cfg' file, send new web page with its MAC 
and IP addresses, and reboot MCU.

Known issues
------------

Sometimes after countdown web client cannot access MCU, reconnecting to AP, and 
refreshing 'http://192.168.1.1' page helps.


Licensing
---------

Please see the file called LICENSE

