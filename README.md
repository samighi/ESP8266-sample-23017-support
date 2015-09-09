# ESP8266-sample-23017-support
ESP8266 sample of advance server + 23017 I2C expander support 

<B>Requirement</B>

ESP8266-12 module
MCP23017 I2C expander
Arudino IDE 1.6.5 
Preferences - Board Manager URL -  http://arduino.esp8266.com/package_esp8266com_index.json

<B>Setup</B>

Please use this file a a sample of ESP8266 and 23017. 

it uses GPIO4 and GPIO5 for processing. Please note that on some boards, 4 and 5 are reversed. Please experiment to find out. 

The code brings up a webserver on a specific IP Address, using that IP address

<code>IP address: 10.0.55.117
MDNS responder started
HTTP server started</code>


<B>Testing</B>

Turn off all lights

    http://serveripaddress/ledtest?A=0&B=0  

Turn on all A or B side of the lights (0-255)

    http://serveripaddress/ledtest?A=255&B=0 
    http://serveripaddress/ledtest?A=0&B=255

Not that giving A to a binary value of each LED, will set all lights to the current requirement. 

You must pass it the complete value

<B>BASH testing</B>

you can use curl to test each LED 

for i in `seq 1 255`;         do      curl -s http://10.0.55.117/ledtest?A=$i\&B=$j -o x.x; sleep .05 ;         done  

for j in `seq 1 255`;         do      curl -s http://10.0.55.117/ledtest?A=$i\&B=$j -o x.x; sleep .05 ;         done  


