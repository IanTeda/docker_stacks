# Unifi Application

## Device Adoption

For Unifi to adopt other devices, e.g. an Access Point, it is required to change the inform IP address. Because Unifi runs inside Docker by default it uses an IP address not accessible by other devices. To change this go to Settings > System > Advanced and set the Inform Host to a hostname or IP address accessible by your devices. Additionally the checkbox "Override" has to be checked, so that devices can connect to the controller during adoption (devices use the inform-endpoint during adoption).

Note that you must use 8080:8080. If you MUST change the port, it must be changed on both sides and manually changed in your system.properties file. Otherwise, devices will initially communicate and then break after.

**Please note, Unifi change the location of this option every few releases so if it's not where it says, search for "Inform" or "Inform Host" in the settings.**

In order to manually adopt a device take these steps:

```
ssh ubnt@$AP-IP
set-inform http://$address:8080/inform
```

The default device password is `ubnt`. `$address` is the IP address of the host you are running this container on and `$AP-IP` is the Access Point IP address.

When using a Security Gateway (router) it could be that network connected devices are unable to obtain an ip address. This can be fixed by setting "DHCP Gateway IP", under Settings > Networks > network_name, to a correct (and accessible) ip address.

## Reference

- [linuxserver/docker-unifi-network-application](https://github.com/linuxserver/docker-unifi-network-application)