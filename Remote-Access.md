Firefly Luciferin and Glow Worm Luciferin each have a web interface. Use **Firefly's interface to control capture and configure your lighting setup**; use **Glow Worm's interface to configure the LED controller and its standalone effects**.

## Control Firefly from your browser

Control Firefly from your phone while sitting on the couch, or from another computer on your local network. The web interface is available whether Firefly runs on a PC or a Raspberry Pi, with or without a desktop.

1. Start Firefly on the computer or Raspberry Pi that captures the image.
2. On that machine, open `http://localhost:8091`, or use the web interface entry in Firefly's tray menu.
3. From your phone or another computer on the same network, replace `localhost` with the **IP address of the machine running Firefly**, for example `http://192.168.1.50:8091`.

You can configure capture and devices, manage profiles, adjust colors and brightness, and control lighting from the browser.

<!-- Screenshot: Firefly web interface on a phone, showing capture controls and settings. -->

Firefly automatically detects whether a desktop is available. When it is, you can also use the **dedicated desktop interface**, which offers some additional customization options. The web interface remains available in both modes.

The **Web / MCP server** setting in the **Mode** tab enables browser control and AI integration. It is enabled by default. For control through an AI assistant, see [MCP and AI Agents](https://github.com/sblantipodi/firefly_luciferin/wiki/MCP-and-AI-Agents).

### If the page does not open

- Keep Firefly running and check that **Web / MCP server** is enabled.
- On your phone, use the host's IP address: `localhost` refers to the phone itself.
- Check that both devices are on the same local network and that the host's firewall allows TCP port **8091**. Live preview also uses TCP port **8092** for its connection setup; see [Linux support](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support#firewall).

## Configure WiFi, Ethernet, MQTT on Glow Worm Luciferin FULL firmware using the Web Installer

For network connections, install **Glow Worm Luciferin FULL** on your LED controller. **MQTT is optional**: WiFi and Ethernet streaming do not require an MQTT broker.

1. Connect the controller to your computer by USB and open the [Luciferin Web Installer](https://sblantipodi.github.io/glow_worm_luciferin).
2. Click **Install FULL** and select the controller's serial port.

<img width="450" alt="Install FULL firmware in the Web Installer" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/1_webinstaller.png?raw=true">

3. After installation, enter your WiFi credentials.

<img width="450" alt="Enter WiFi credentials" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/4_webinstaller.png?raw=true">

4. Click **Visit Device** to open the controller's web interface.

<img width="450" alt="Open the controller web interface" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/5_webinstaller.png?raw=true">

5. Open the menu in the top right to access firmware settings. Enable **Ethernet** if you have a [compatible Ethernet controller](https://github.com/sblantipodi/firefly_luciferin/wiki/Compatible-Hardware#ethernet-devices), or **MQTT** if you want to use a broker.

<img width="400" alt="Glow Worm network settings" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/web_installer/7_webinstaller.png?raw=true">

If the WiFi credentials are incorrect or have changed, use USB provisioning below to update them without reflashing. You can also configure the controller through its [WiFi access point](https://github.com/sblantipodi/firefly_luciferin/wiki/WiFi-and-MQTT-configuration-using-the-Luciferin-Access-Point).

## Provision directly from Firefly Luciferin

Firefly can configure the controller's WiFi and MQTT settings over USB. This is also useful when a controller is offline after a WiFi password change.

1. Connect the controller to the machine running Firefly by USB.
2. Open the **Network** tab and select **Provisioning**.
3. Follow the provisioning dialog to enter and apply the connection settings.

<img width="400" alt="Provision a controller from Firefly" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/provisioning.png?raw=true">

<!-- Screenshot: updated Firefly provisioning dialog and its location in the Network tab. -->

## Configure Firefly Luciferin for FULL firmware

1. In the **Mode** tab, select **FULL** firmware.
2. In the **Devices** tab, select the controller in **Output device**.
3. Enable MQTT in the **Network** tab only if you intend to use it. Configure both Firefly and Glow Worm for the same broker and matching topic settings.

Firefly sends the captured colors to the selected controller over WiFi, Ethernet, or USB. For the complete capture setup, see [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start).

<!-- Replace the following older screenshot with separate current screenshots of Mode, Devices (Output device), and optional MQTT settings. -->
<img width="750" alt="Firefly firmware and network settings in an earlier interface" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/enable_wifi_mixed.png?raw=true">

## Luciferin Web Interface

**Glow Worm Luciferin FULL** has its own web interface for controller settings, colors, brightness, and standalone lighting effects. Firefly must still run on a PC or Raspberry Pi for screen or HDMI capture.

Open the **controller's IP address** in your browser, for example `http://192.168.1.82`. Where supported, you can also use its device name: `http://your_device_name.local`.

<img width="750" alt="Glow Worm controller web interface" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/web_interface.jpg?raw=true">

In Firefly's **Devices** tab, click the controller's IP address to open this interface.

<img width="400" alt="Open Glow Worm from the Devices tab" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/webinterfaceaccess.png?raw=true">

The **Save state** button stores the current color, effect, brightness, and on/off state so they can be restored after a controller reboot.

## MQTT Support

MQTT lets you control Glow Worm through an MQTT client or integrate it with Home Assistant. Enable and configure MQTT in both components when using Firefly with MQTT.

![MQTT lighting controls on a phone](https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/HA_mobile_client_screenshot.jpg?raw=true)

### Default topic

Publish commands to:

```text
lights/glowwormluciferin/set
```

If you have changed the device topic, use the corresponding topic instead.

### Turn the LED strip on or off

Publish one JSON message at a time:

```json
{"state": "ON"}
```

```json
{"state": "OFF"}
```

To select a standalone effect:

```json
{"state": "ON", "effect": "rainbow"}
```

For Home Assistant integration, see [Home Assistant](https://github.com/sblantipodi/firefly_luciferin/wiki/Home-Automation-configs).