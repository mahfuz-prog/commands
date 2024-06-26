# Ubuntu applications

##### ssh
```bash
ssh-keygen -t ed25519 -C 'comment'	# create keys using cryptography

# ~/.ssh
.ssh dir should have permission 700
files of .ssh dir should have 600

sudo systemctl restart sshd.service  	# restart services

# multiple ssh config
~/.ssh/config				# config file loaction
----------------------------------|
Host debian			  |	# Host whatever
    Hostname 34.131.146.239	  |	# if of domain
    User debian			  |	# username of cloud machine
    IdentityFile ~/.ssh/id_debian |	# ssh keys file
----------------------------------|
ssh debian				# login using ssh


# if has passphrase 
eval $(ssh-agent)			# it cash the key for per session
ps aux | grep [process_id]		# p_id get from eval, running in bg
ssh-add ~/.ssh/key_name			# passphrase to agent
```

##### ufw
```bash
sudo ufw status	numbered				    	# status of ufw
sudo ufw reset							# reset ufw

sudo ufw default allow outgoing					# allow outgoing traffic from server
sudo ufw default deny incoming					# deny all incoming traffic

cat /etc/services						# see all the ports
sudo ufw allow ssh						# allow to access port from anywhere
sudo ufw deny ssh						# deny ssh port access
sudo ufw delete [number]				    	# delete the rule for num

sudo ufw allow from ip to any port 22 proto tcp

sudo ufw enable							        # enable ufw
sudo ufw disable						        # disable ufw
``` 

##### Psql
```bash
sudo apt-get install postgresql postgresql-contrib
service postgresql						# usages of postgres
service postgresql status					# give the status			
/etc/postgresql/14/main/postgresql.conf 			# config file location
```
