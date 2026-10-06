Luciferin has two components to keep compatible: **Firefly**, running on your PC or Raspberry Pi, and **Glow Worm firmware**, running on each LED controller.

Check installed versions in Firefly's **Devices** tab. When upgrading Firefly, follow the release notes for the required controller firmware.

<img width="400" alt="Devices and installed versions" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/device_tab.jpg?raw=true">

### Automatic Updates

The **Check for updates** setting is in the **Mode** tab. When enabled, Firefly checks for new application and controller versions. You can also request a check through **Update** in the desktop tray menu.

<img width="700" alt="Update changelog" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/update_changelog.jpg?raw=true">

With a desktop, Firefly displays the available update and guides you through the download and installation. Updates can stop capture and restart components.

<img width="400" alt="Update download progress" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/downloading.jpg?raw=true">

<!-- Screenshot: current Check for updates setting in Mode and update controls/status in the web interface. -->

## Application updates without a desktop

Without a desktop, Firefly reports an available application update in its status/logs rather than launching a graphical installer. Install the new package using the same method you used originally, stopping the application or service first.

For **Flatpak, Snap, or other package managed installations**, update through the package manager or store. Do not expect a native DEB/RPM installer to update a sandboxed application.

## Full Firmware Updates

Firefly can update compatible **FULL** controllers over the network, including multiple detected controllers in one update operation.

<img width="400" alt="Firmware update available" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/new_version.jpg?raw=true">

With a desktop, follow the firmware update dialog. Without a desktop, eligible controllers can be updated automatically when update checks are enabled. Controllers that are too old or do not support this update path require a manual update.

Capture is paused during the operation. Keep controllers powered and connected until the update completes.

<img width="400" alt="Firmware update result" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/upgrade_success.jpg?raw=true">

If an update fails, check the reported status and controller connectivity before retrying. Do not assume every board provides automatic rollback.

## Light Firmware Updates

Update **LIGHT** firmware manually through the [Web Installer](https://sblantipodi.github.io/glow_worm_luciferin) or use the matching binary from [Glow Worm releases](https://github.com/sblantipodi/glow_worm_luciferin/releases) with the [esptool guide](https://github.com/sblantipodi/firefly_luciferin/wiki/How-to-flash-Glow-Worm-Luciferin-firmware-via-esptool).

For development versions, see [How to install a BETA](https://github.com/sblantipodi/firefly_luciferin/wiki/How-to-install-a-BETA).
