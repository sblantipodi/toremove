If your Glow Worm controller goes offline after a WiFi or MQTT password change, first **update its connection settings**. A changed password does not normally require erasing or reinstalling firmware.

### 1) Provision directly from Firefly Luciferin

Connect the controller by USB and open **Network → Provisioning** in Firefly. Follow the [USB provisioning guide](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access#provision-directly-from-firefly-luciferin) to update WiFi and MQTT settings.

### 2) Using the ESP WiFi Access Point (no USB required)

FULL firmware provides a recovery path when the saved network cannot be reached:

1. Power the controller on and let it attempt to reconnect.
2. After repeated connection failures and the recovery delay, the LEDs turn **red**.
3. Reboot during the recovery sequence to advance through **green**, **blue**, and finally **orange**.
4. When orange appears, connect your phone or computer to the controller's WiFi access point.
5. Open [http://192.168.4.1](http://192.168.4.1) and store the corrected settings.

The initial red state is followed by three recovery reboots; the colors are the useful indication of the current step. If normal connectivity returns, the recovery sequence is cleared.

<img width="450" alt="Controller connection settings" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/7_webinstaller.png?raw=true">

See [Access Point configuration](https://github.com/sblantipodi/firefly_luciferin/wiki/WiFi-and-MQTT-configuration-using-the-Luciferin-Access-Point) for the available settings.

### 3) Using USB and Web Installer

If provisioning or recovery does not resolve the problem, use the [Web Installer](https://sblantipodi.github.io/glow_worm_luciferin) to reinstall the firmware matching your board.

Select an erase option only when you intend to clear saved settings. After erasing, configure the controller and its network connection again.
