Profiles save different lighting setups so you can switch quickly: for example, separate settings for gaming, movies, or a different capture source. Manage and apply them from Firefly's web interface, or use the profile selector and tray menu when a desktop is available.

<!-- Screenshot: profile selection, creation, and apply controls in the web interface. -->

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/profiles.jpg?raw=true">

Profiles can be added using the `+` button and removed using the `-` button.

The tray icon allows for quick switching between profiles.  
You can also apply a profile by clicking the `✔` button in the **Misc** tab.

<img width="300" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/tray_icon_profiles.png?raw=true">

The default profile cannot be removed and is automatically loaded when the application starts for the first time.

Some profiles may include changes that require Firefly Luciferin to restart automatically.  
When a restart is required, the `✔` or `Save` button will turn red.

## Advanced Profile Settings dialog
*(This feature is available on Windows only)*

Once a profile is active, the apply `✔` button is replaced by a menu button **`☰`**.  
Clicking this button opens the **Advanced Profile Settings dialog**.

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/profile_dialog.png?raw=true">

The Advanced Profile Settings dialog allows you to define triggers to automatically apply a profile when a specific application is running or when certain conditions are met.

You can configure the following triggers:
- Monitor a running process (for example `steam.exe`) and apply the profile when it is detected
- Monitor the active window and apply the profile when it enters fullscreen mode
- Monitor CPU and GPU load and apply the profile when a specified threshold is exceeded

### Starting a profile from the command line

You can start Luciferin with a specific profile directly from the command line:

```text
FireflyLuciferin.exe 1 "profilename"
```

Where:

* `FireflyLuciferin.exe` is the Luciferin executable
* `1` is the instance number (1,2 or 3 for the three monitors)
* `"profilename"` is the profile name

Add `-h` at the end only if you want to force operation without the desktop interface. Normally Firefly detects desktop availability automatically; web control is available in either mode.
