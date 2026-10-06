Firefly discovers Glow Worm FULL controllers through local network broadcasts. On a typical home network, select the discovered controller in **Devices → Output device**.

## When discovery does not work

Broadcasts normally stay within their network segment. A separate VLAN, routed subnet, guest WiFi, or client isolation setting can prevent discovery even when a controller has a working connection.

Check the controller's IP address and the [firewall ports](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support#firewall). If Firefly can reach the controller but cannot discover it, enter its address manually using Firefly's static IP setting.

<img width="400" alt="Manual controller IP setting" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/static_ip.jpg?raw=true">

<!-- Screenshot: current manual-IP setting and Devices output selection. -->

Entering an address in Firefly **does not assign that address to the controller**. The controller must already be reachable there.

## Keep the address stable

For a manually selected address, a **DHCP reservation** in your router keeps the same IP for the controller while it continues using DHCP.

Alternatively, configure a static address in the controller's own [Glow Worm web interface](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access#luciferin-web-interface), with the correct gateway and network settings.

## MQTT as an alternative discovery path

MQTT is optional. When configured in both Firefly and Glow Worm, device status can reach Firefly through the broker, which can help when UDP discovery is unavailable.

The lighting stream still needs a working connection for its selected transport. MQTT discovery does not remove the need for routing and firewall access between Firefly and the controller.
