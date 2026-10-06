Run Firefly as a **user service** when you want HDMI capture to start on a Linux host without logging into a desktop. This suits a Raspberry Pi beside the TV, controlled through Firefly's web interface.

For PC screen capture, use [desktop autostart](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support#how-to-configure-luciferin-autostart) instead: capturing a desktop requires an active graphical session and, on Wayland, its screen sharing portal.

## Prepare the setup

Install Firefly, configure the USB capture input and LED controller, and verify that capture works before enabling the service. Enable **Turn LED ON** if capture should start with Firefly, and keep **Web / MCP server** enabled.

Run the following commands as the user who will own the configuration. Avoid starting a second Firefly instance manually while the service is running.

## Create the service

Create the user service directory:

```bash
mkdir -p ~/.config/systemd/user
nano ~/.config/systemd/user/luciferin.service
```

For a **native DEB/RPM installation**, save this unit:

```ini
[Unit]
Description=Firefly Luciferin HDMI capture

[Service]
Type=simple
ExecStart=/opt/fireflyluciferin/bin/FireflyLuciferin -h
Restart=on-failure
RestartSec=5

[Install]
WantedBy=default.target
```

The `-h` option explicitly keeps this service without a desktop interface. Normal interactive launches detect desktop availability automatically.

### Flatpak alternative

For a Flatpak installation, replace **ExecStart** with:

```ini
ExecStart=/usr/bin/flatpak run org.dpsoftware.FireflyLuciferin -h
```

Confirm the Flatpak executable path on your distribution. The application and its USB/video permissions must be available to the service user; the native installation path does not apply to Flatpak.

<!-- Screenshot: working Raspberry HDMI setup controlled through the Firefly web interface. -->

## Enable startup without login

Enable lingering for the current user so their service manager runs at boot and remains active without a login:

```bash
sudo loginctl enable-linger "$USER"
systemctl --user daemon-reload
systemctl --user enable --now luciferin.service
```

The service runs under that user's account and uses that user's Firefly configuration. It needs access to the USB capture device and any audio source you intend to use.

## Control and inspect the service

```bash
systemctl --user status luciferin.service
journalctl --user -u luciferin.service -b
```

To stop or restart it:

```bash
systemctl --user stop luciferin.service
systemctl --user restart luciferin.service
```

From your phone or another computer on the same network, open `http://HOST_IP:8091`. If it does not open, check the service logs and the [firewall ports](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support#firewall).

## Disable the service

```bash
systemctl --user disable --now luciferin.service
```

If no other user services need to run without login, you can also disable lingering:

```bash
sudo loginctl disable-linger "$USER"
```

See the [systemd loginctl documentation](https://www.freedesktop.org/software/systemd/man/latest/loginctl.html) for the behavior of lingering.
