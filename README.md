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
