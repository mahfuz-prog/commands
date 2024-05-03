# Bash commands

##### Guide
```bash
[command] [option]
whatis [command]			# tells about the command
which [command]				# gives dir of command
man [command]				# gives all options
```

##### Users
```bash
whoami
sudo useradd username -m -s /usr/bin/bash -g users		# add user
sudo passwd username						# change password
adduser username sudo						# add the user sudo group
sudo userdel -r username					# delete user
su username							# Switch user
```

##### Groups
```bash
cat /etc/group				# show groups
sudo groupadd grpname			# add group
sudo groupdel grpname			# delete group
sudo gpasswd -a username grpname	# add user to grp
sudo gpasswd -d username grpname	# remove user from grp
```

##### Permission
```bash
d = directory
r = read
w = write
x = execute
- = no permission

drwxr-xr-x = d[dir] rwx[user] r-x[group] r-x[other]

u = user
g = group
o = other

u-w = subtract user write permission
u+w = add user write permission
chmod u-w dir					

4 = read
2 = write
1 = execute
0 = no permission

chmod 7[user] 5[group] 4[other] filename

4+2+1 = 7 read, write, execute
4+1 = 5 read, write
4 = read
```

##### Directory & files
```bash
pwd					# present working dir
ls dir/*.html 				# find html in dir
ls -l > output.txt			# save the list in .txt
cd ~ 					# gives home dir
mkdir dir/{sub1,sub2}			# sub1, sub2 inside dir - spacing
touch run.py				# empty file
cp output.txt newdir			# copy .txt to newdir
rm -rv [parent dir]			# delete all sub dir and files
cat output.txt				# content of this file
cat 1.txt >> 2.txt 			# append 1.txt content in 2.txt
less output.txt				# show only some content, in terminal /searchword
```

##### Install & uninstall
```bash
sudo apt list --installed		# installed app
sudo apt-get update			# list in /etc/apt/sources.list
sudo apt-get remove --purge app		# uninstall app with config
sudo apt-get autoremove			# uninstall dependency packages
sudo apt autoclean			# remove apt cache
```

##### Resources
```bash
nproc --all				# number of cores
top					# show all tasks
htop					# system info
du -sh 					# shows current dir used disk
free -m					# gives memory usages in mb
watch -n 1 free -m 			# execute the command every 1 sec
```

##### Network
```bash
ifconfig				# give network info
netstat -ie				# same as ifconfig
sudo ifconfig eth0 up			# up for connect
sudo ifconfig eth0 down			# down for disconnect

netstat -a | less			# connections over network
```

##### Monitoring and logging
```bash
ls -la /var/log/				# log files location
cat /var/log/auth.log | grep -e 'login'		# find a pattern in log

who						# gives loggedin users
whowatch					# all user info
last -aiF					# last login
lastb -adF root					# last failed login attempts
lastlog -u root					# gives the last login of user
```

##### Bash scripting
```bash
nano script.sh			# add #!bashdir than command
```

##### Service
```bash
sudo nano /etc/systemd/system/myservice.service			            # create new service 

---------------------------------------------------------------
[Unit]
After=network.target

[Service]
WorkingDirectory=/home/username/my-scraper
ExecStart=/home/username/my-scraper/.env/bin/python3 scraper.py
---------------------------------------------------------------

sudo systemctl daemon-reload                                        # inform systemd about our created daemon
sudo systemctl start myservice                                      # start service
sudo systemctl status myservice                                     # see the status
sudo systemctl restart myservice                                    # restart the service
sudo systemctl stop myservice                                       # stop service
```