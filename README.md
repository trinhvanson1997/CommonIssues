# Common Issues

### Error network manager disappear on Settings (ubuntu 20.04)
1. Check whether package is installed?
```
sudo dpkg -s linux-modules-extra-$(uname -r)
```
2. Download driver on repository at [link](https://mirrors.edge.kernel.org/ubuntu/pool/main/l/linux/)
3. Copy driver to machine and run
```
sudo dpkg -i linux*.deb
```
https://askubuntu.com/questions/1312096/wired-network-settings-missing-in-ubuntu-desktop-20-10

https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-pci-express-software
