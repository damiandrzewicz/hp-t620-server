# balenaEtcher installation on Ubuntu 22.04 host machine

1. Download [image](https://github.com/balena-io/etcher/)
2. Enable the Ubuntu Universe repository
```
sudo add-apt-repository universe
```
3. Open a terminal and navigate to the directory where the BalenaEtcher .deb file is located. For example, if it's in the Downloads folder, run the command:
```
cd ~/Downloads
```
4. Change the ownership of the .deb file to your user account by executing the following command:
```
sudo chown $USER:$USER balena-etcher_1.18.4_amd64.deb
```
5. Install BalenaEtcher using the updated ownership of the file by running the command:
```
sudo dpkg -i balena-etcher_*_amd64.deb
```


