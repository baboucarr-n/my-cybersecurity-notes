# Analyzing Networks -- ifconfig and iwconfig

*Date: 30th April, 2026*

## ifconfig

ifconfig is used to analyze, examine, and interact with active network interfaces.

```
ifconfig
```

Example output:
```
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.21.105.63  netmask 255.255.240.0  broadcast 172.21.111.255
        inet6 fe80::215:5dff:fe35:f19d  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:35:f1:9d  txqueuelen 1000  (Ethernet)
        RX packets 13  bytes 818 (818.0 B)
        TX packets 201  bytes 14826 (14.8 KB)

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
```

Breaking this down:

- **eth0** -- the first detected wired network interface. Linux numbers these starting from 0, so more interfaces would show up as eth1, eth2, etc.
  - `inet` -- the current IP address assigned to this interface
  - broadcast -- the address used to send info to other IPs on the same subnet
  - netmask -- determines which part of the IP address belongs to the local network

- **lo (loopback)** -- also called localhost. A software-only address that connects the machine to itself. Only things running locally can use it -- useful for testing something on your own system, like a local web server.

- **wlan0** -- shows up if a wireless interface/adapter is present. Also shows the MAC address (HWaddr) of that device.

This information is core to understanding and manipulating LAN settings -- a genuinely essential skill in security work.

## iwconfig

Used to get info on wireless adapters specifically.

**Still need to dig deeper into this one** -- especially before doing any wireless pentesting work.

## Changing Network Information

Being able to change your IP and other network settings is useful -- for example, appearing as a trusted device on another network, or spoofing an IP source during something like a DoS attack to help evade forensic tracing.

### Changing IP Address

```
ifconfig eth0 192.168.181.115
```
General syntax: `ifconfig [interface] [new IP]`

If nothing prints after running it, that's actually a good sign -- it means the change went through.

**Problem I ran into:** needed superuser privileges to actually run this.

### Changing Netmask and Broadcast Address

```
ifconfig eth0 netmask 255.255.0.0 broadcast 192.168.1.255
```
Same deal -- no error output means success. Run `ifconfig` again afterward to confirm the values actually changed.

### MAC Address Spoofing

Steps:
```
ifconfig eth0 down
ifconfig eth0 hw ether 00:11:22:33:44:55
ifconfig eth0 up
```
- Take the interface down first
- Assign the new (spoofed) MAC address using hw ether
- Bring the interface back up for the change to apply