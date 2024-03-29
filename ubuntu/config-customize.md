# Config & customize ubuntu

##### Windows powershell
```bash
wsl -l -v (see version)
wsl --set-version Ubuntu-22.04 2 (change version)
wsl --set-default-version 2 (set a default version)

ubuntu2204 config --default-user root 				# root default
```

##### Annoying bell sound
```bash
sudo nano /etc/inputrc				# file location
set bell-style none 				# uncomment this line
```