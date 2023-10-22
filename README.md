# Common Issues

### Error network settings disappear on Settings after run `sudo apt autoremove` or upgrade (ubuntu 22.04)
[caused by](https://askubuntu.com/questions/1347827/no-wifi-ethernet-or-gpu-after-sudo-apt-upgrade-on-ubuntu-20-04-2)  
[install kernet header](https://askubuntu.com/questions/75709/how-do-i-install-kernel-header-files)  

1. Check linux package version
```
echo $(uname -r)
example: 6.2.0-35-generic

```

2. Check network config
```
sudo lshw -C network

example:
*-network
     description: Ethernet interface
     product: RTL8125 2.5GbE Controller
     vendor: Realtek Semiconductor Co., Ltd.
     physical id: 0
     bus info: pci@0000:04:00.0
     logical name: enp4s0
     version: 05
     serial: 50:eb:f6:76:2b:29
     size: 100Mbit/s
     capacity: 1Gbit/s
     width: 64 bits
     clock: 33MHz
     capabilities: pm msi pciexpress msix vpd bus_master cap_list ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
     configuration: autonegotiation=on broadcast=yes driver=r8125 driverversion=9.010.01-NAPI duplex=full ip=192.168.0.175 latency=0 link=yes multicast=yes port=twisted pair speed=100Mbit/s
     resources: irq:19 ioport:4000(size=256) memory:a3500000-a350ffff memory:a3510000-a3513fff

```

3. Download driver on repository at [linux header & linux hwe](http://security.ubuntu.com/ubuntu/pool/main/l/linux-hwe-6.2/)
example: 
- 	linux-headers-6.2.0-25-generic_6.2.0-25.25~22.04.2_amd64.deb
- 	linux-hwe-6.2-headers-6.2.0-35_6.2.0-35.35~22.04.1_all.deb

4. Install linux header
```
sudo dpkg -i linux-*.deb
```

5. Download ethernet driver for RTL8125 (listed in step 2)
```
https://github.com/awesometic/realtek-r8125-dkms 
```

6. Install ehternet driver
```
sudo dpkg -i realtek-r8125-dkms_9.010.01-2_amd64.deb
```

7. Reboot
```
sudo reboot
```



