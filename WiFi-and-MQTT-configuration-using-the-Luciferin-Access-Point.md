<a name="connect-to-wi-fi-full-firmware-only"></a>

## Connect to WiFi (FULL firmware only)

MQTT is **optional**. Configure it only if you want broker based control or Home Assistant integration.

This is an alternative way to store WiFi credentials on the microcontroller.  
The simplest solution is to use the web installer    
[![Web Installer](https://img.shields.io/website/https/sblantipodi.github.io/glow_worm_luciferin.svg?label=Web%20Installer&down_color=red&down_message=offline&up_color=4bc51d&up_message=online&logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAIAAAACACAMAAAD04JH5AAAAD1BMVEUAAAD%2F%2F%2F%2F%2F%2F%2F%2F%2FVyL%2F%2F%2F8bK2t7AAAAA3RSTlMAARYXuUDOAAAAhklEQVR42u3WyQ2AMAwEQAz9lxxCCRCuONHse2XPy3JsS98EAAAAAAAAQDpAfLywAgAADAuoJ716dw4AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMAwgLcCAACQH%2FB3AAAAAAAAAPoDWovrxYdjBwAAmA7QerAKAADANICnD0sBAADIDjgAPijZuQgZskEAAAAASUVORK5CYII%3D)](https://sblantipodi.github.io/glow_worm_luciferin)  
or to [**provision directly from Firefly Luciferin**](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access#provision-directly-from-firefly-luciferin).

If you haven't configured WiFi using the Web Installer, thanks to [Arduino Bootstrapper](https://github.com/sblantipodi/arduino_bootstrapper),  
**Glow Worm Luciferin** firmware starts an access point for easy configuration via a web browser.

Please connect to the access point. If you search for WiFi networks, you will find your ESP **device named GLOW_WORM**.  
Once connected, go to [http://192.168.4.1](http://192.168.4.1) and you will access a GUI where you can enter all the passwords without the need for hardcoding them.

<img align="center" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/7_webinstaller.png?raw=true">

1) **Device Name:** The device name you will use in Firefly Luciferin to point to your microcontroller. If you have multiple devices, choose a different device name.
2) **IP Address:** The IP address that your ESP should use (optional, leave blank for DHCP).
3) **SSID:** Your WiFi SSID.
4) **WiFi Password:** Your WiFi password.
5) **OTA Password:** Password used to update Luciferin via wireless.
6) **MQTT Server IP:** The IP address of your MQTT server (optional).
7) **MQTT Server Port:** The port of your MQTT server (optional).
8) **MQTT Username:** The username for your MQTT server (optional).
9) **MQTT Password:** Your MQTT password (optional).
10) **GPIO PIN FOR THE LED STRIP:** Choose the data pin matching your controller and wiring; supported pins and defaults differ by chip and board.
    Please read here to understand what is the [best GPIO](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate) for your use case.

**Please double check your input before clicking the 'Store config' button.**  
If the connection settings are wrong, update them through [USB provisioning or Access Point recovery](https://github.com/sblantipodi/firefly_luciferin/wiki/Device-reset) before considering reflashing.

**Note:** The Access Point stops working once WiFi credentials are stored into the microcontroller.

Once the controller is connected, configure Firefly on your PC or Raspberry Pi using its desktop or web interface.
How to [here](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access)
