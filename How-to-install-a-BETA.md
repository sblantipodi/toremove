Use a **BETA/development build** when you want to test an upcoming feature or help investigate a problem. Use stable releases for a setup you want to keep on the regular release channel.

## Before installing

Back up your Firefly configuration folder, including profiles and custom `cube_lut` files. Installation normally keeps your configuration, but a development build can migrate settings.

Find the folder through [Debug](https://github.com/sblantipodi/firefly_luciferin/wiki/Debug#find-configuration-and-logs). Check the build's notes for any required Glow Worm firmware update.

## Install a development build

1. Open the [Firefly build workflow](https://github.com/sblantipodi/firefly_luciferin/actions/workflows/build.yml) and select a successful run for the feature/branch you want to test. GitHub sign in is required to download its artifacts.
2. Download the artifact matching your system: Windows, Linux x86-64, or Linux ARM64.
3. Extract the artifact and install the package. Stop the running application or service first.
4. Start Firefly and verify capture and controller connectivity.

For Flatpak or Snap, follow the distribution's available channels rather than assuming a workflow artifact updates the store package.

## Development firmware

The [Glow Worm Web Installer](https://sblantipodi.github.io/glow_worm_luciferin) lets you select a BETA version when one is available.

FULL firmware may also be updated through Firefly when the build selects that firmware channel and the controller supports automatic updates. LIGHT firmware is updated manually. See [Update management](https://github.com/sblantipodi/firefly_luciferin/wiki/Luciferin-update-management).

## Return to stable

Install the current stable Firefly release and its compatible Glow Worm firmware. The updater can offer stable versions as they become available; this does not mean every future development build will be installed automatically.

If older software cannot read settings migrated by a development build, restore your configuration backup with Firefly stopped.
