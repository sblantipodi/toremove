Logs help identify whether a problem comes from capture, the host, the network, or the controller.

## Find configuration and logs

| Installation | Configuration folder |
| --- | --- |
| Windows | `FireflyLuciferin` inside your Documents folder |
| Native Linux | `$XDG_CONFIG_HOME/FireflyLuciferin`, normally `~/.config/FireflyLuciferin` |
| Flatpak / Snap | The application's sandbox configuration folder |

Windows Documents may be redirected, for example to OneDrive. Logs are in the **logs** subfolder; configuration files are in its **parent folder**, not inside logs.

The default configuration is `FireflyLuciferin.yaml`. Additional monitor instances use `FireflyLuciferin_2.yaml` and `FireflyLuciferin_3.yaml`; profiles have their own saved configuration.

## Enable debug logging

1. Stop Firefly so it does not overwrite your manual edit.
2. Back up the configuration file used by the affected instance/profile.
3. Set:

```yaml
runtimeLogLevel: "DEBUG"
```

4. Restart Firefly and reproduce the problem.
5. Read the resulting files in **logs**. Restore **INFO** when finished.

Older configurations used `extendedLog`; current Firefly migrates that key to `runtimeLogLevel`.

You can also override the configured level with the **LUCIFERIN_LOG_LEVEL** environment variable. For a native Linux launch:

```bash
LUCIFERIN_LOG_LEVEL=DEBUG /opt/fireflyluciferin/bin/FireflyLuciferin
```

| Level | Purpose |
| --- | --- |
| TRACE | Most detailed diagnostic output |
| DEBUG | Detailed troubleshooting |
| INFO | Normal operation; default |
| WARN | Conditions that may need attention |
| ERROR | Errors encountered during operation |
| ALL | Enable all logging |
| OFF | Disable logging |

## What to check first

- **Black or missing HDMI picture:** check the splitter/capture-card connections and the selected USB input. Use web live preview to inspect the incoming picture.
- **Screen capture problems:** start with **AUTO**, then compare a compatible alternate backend. On Wayland, check the screen sharing prompt.
- **Controller missing:** check its network or USB connection, selected output device, and [discovery/firewall settings](https://github.com/sblantipodi/firefly_luciferin/wiki/Static-IP-and-auto-discovery).
- **Web interface unavailable:** confirm Firefly is running, the Web / MCP server setting is enabled, and you are using the host's IP with port **8091**.
- **Service startup problems:** use `journalctl --user -u luciferin.service` as well as the application logs.

When requesting help, include the Firefly/Glow Worm versions, operating system, capture source and method, connection type, and relevant log excerpt. Remove passwords or broker credentials from configuration files before sharing them.
