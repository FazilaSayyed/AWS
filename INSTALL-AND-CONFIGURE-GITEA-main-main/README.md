<h3>Step 1: Create Instance</h3> <strong>(MUST HAVE 3000 PORT IN SECURITY GROUP)</strong>

![image](https://github.com/user-attachments/assets/dd1a575b-264b-4073-9c3f-bb8793aa1a3a)

<h2>Step 2: Connect Instance </h2>

```
sudo -i
sudo apt update
sudo apt install postgresql postgresql-contrib -y (Install PostgreSQL)
sudo systemctl enable postgresql.service
sudo -i -u postgres
psql
CREATE ROLE gitea WITH LOGIN PASSWORD 'gitea';
CREATE DATABASE giteadb WITH OWNER gitea TEMPLATE template0 ENCODING UTF8 LC_COLLATE 'en_US.UTF-8' LC_CTYPE 'en_US.UTF-8';
\q
exit
sudo vim /etc/postgresql/16/main/pg_hba.conf
```

<strong>(host  all  all 0.0.0.0/0 scram-sha-256  edit like this line)</strong><br>

![image](https://github.com/user-attachments/assets/c2e1e290-5b51-416d-a701-3848926f7438)
```
sudo vim /etc/postgresql/16/main/postgresql.conf
```
**(listen_addresses = '*' edit this line)**<br>

![image](https://github.com/user-attachments/assets/cc4bda94-9952-41eb-9d60-ffea995f47da)

**(reset password for ubuntu) <br>**
```
sudo passwd ubuntu
service postgresql restart
```
**(Update the APT package cache, upgrade the already installed software and install Git)<br>**
```
sudo apt update && sudo apt upgrade -y && sudo apt install git -y
```
**(Download gitea binary and make it executable)**
```
wget -O gitea https://dl.gitea.com/gitea/1.21/gitea-1.21-linux-amd64
chmod +x gitea
```
**(Add the user that will run the Gitea application)<br>**
```
sudo adduser --system --shell /bin/bash --gecos 'Git Version Control' --group --disabled-password --home /home/git git
```
**(Create the folder structure that is used by Gitea to store data) <br>**
```
sudo mkdir -p /var/lib/gitea/custom
sudo mkdir -p /var/lib/gitea/data
sudo mkdir -p /var/lib/gitea/log
sudo chown -R git:git /var/lib/gitea/
sudo chmod -R 750 /var/lib/gitea/
sudo mkdir /etc/gitea
sudo chown root:git /etc/gitea
sudo chmod 770 /etc/gitea
```
**(Set the working directory of Gitea)<br>**
```
export GITEA_WORK_DIR=/var/lib/gitea/
```
**(Copy the Gitea binary file to /usr/local/bin to make it available system-wide)<br>**
```
sudo cp gitea /usr/local/bin/gitea
```
**(Create a systemd service for Gitea)<br>**
```
sudo vim /etc/systemd/system/gitea.service
```
**(Copy the following content into the service file)<br>**
```
[Unit]
Description=Gitea (Git with a cup of tea)
After=syslog.target
After=network.target
[Service]
RestartSec=2s
Type=simple
User=git
Group=git
WorkingDirectory=/var/lib/gitea/
ExecStart=/usr/local/bin/gitea web -c /etc/gitea/app.ini
Restart=always
Environment=USER=git HOME=/home/git GITEA_WORK_DIR=/var/lib/gitea

[Install]
WantedBy=multi-user.target
```
**( Enable the service and start Gitea at system boot) <br>**
```
systemctl enable gitea.service
systemctl start gitea.service
```
<h3>Step 3: Paste the public IP of Instance with 3000 port</h3>

![image](https://github.com/user-attachments/assets/e5767fd1-4a47-4295-84d2-84ab791f841c)

<h3>Step 4: Create a new file in repository</h3>

![image](https://github.com/user-attachments/assets/34070127-97b7-49ff-9542-90cb7303bc60)

```
git clone http://65.0.76.229:3000/Aamantamboli/new.git
cd new/
```
<h3>Step 5: Now pull it from repository</h3>

![image](https://github.com/user-attachments/assets/87f9b50f-8a45-44e1-9449-fa1b075fc8b0)

**Successfully configure Gitea and pull repository**
