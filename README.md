# piSociEty
Inspired from Mr. Robot I started developing this framework which can create 3vil twins, ddos Wireless networks, bypass HSTS(partial) and many more...This project is still in progress and social engineering of login pages is still in progress...

Install all dependencies
---------------------------------------------------------------------------------------------------
```
wget http://ftp.us.debian.org/debian/pool/main/c/capstone/libcapstone-dev_3.0.4-0.2_armhf.deb
wget http://ftp.us.debian.org/debian/pool/main/c/capstone/libcapstone3_3.0.4-0.2_armhf.deb
dpkg -i *
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py
sudo apt-get install screen hostapd macchanger aircrack-ng dnsmasq wireless-tools iw wvdial rfkill figlet libnl-3-dev libnl-genl-3-dev libnl-3-dev libnl-genl-3-dev python-configobj python-flask python-ipy libgmp-dev libgmpxx4ldbl ruby2.1-dev subversion nmap tcpdump mate-terminal libapache2-mod-php5 apache2 dnsutils python-dev python-setuptools libpcap0.8-dev libnetfilter-queue-dev libssl-dev libjpeg-dev libxml2-dev libxslt1-dev libcapstone3 libcapstone-dev libffi-dev file
sudo apt-get update && sudo apt-get dist-upgrade
sudo rpi-update
cd modules/mitmf
pip install virtualenvwrapper
source /usr/local/bin/virtualenvwrapper.sh
source /usr/local/bin/virtualenvwrapper.sh
mkvirtualenv mitmf -p /usr/bin/python2.7
git submodule init && git submodule update --recursive
pip install -r requirements.txt
```
Set up Rouge AP
---------------------------------------------------------------------------------------------------
```
cp dnsmasq /etc/default/dnsmasq
cp dnsmasq.conf /etc/dnsmasq.conf
cp hostapd.conf /etc/hostapd/hostapd.conf
cp hostapd /etc/default/hostapd
**Add /etc/hostapd/hostapd.conf in /etc/init.d/hostapd infront of DAEMON_CONF**
echo -e 'nameserver 8.8.8.8\nnameserver 8.8.4.4' >> /etc/resolv.conf
chattr +i /etc/resolv.conf
```
Modules directory contain modules needed to be executed. Currently it supports the following
---------------------------------------------------------------------------------------------------
Tcpdump  
Mitmf  
Airstrike  
Nuke  
Show_clients  
Clean_slate_protocol  

Setup Router Phisher
---------------------------------------------------------------------------------------------------
```
sudo cp -r * /var/www/html/
chmod ugo+w /var/www/html/mypasswd
apache2ctl restart
mkdir /etc/apache2/ssl
```

Make sure Certificate's common name should be localhost
---------------------------------------------------------------------------------------------------
```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt
echo 'ServerName localhost' >> /etc/apache2/apache2.conf
cp {000-default.conf,default-ssl.conf} /etc/apache2/sites-available/
cd /etc/apache2/sites-available/
a2ensite default-ssl.conf
a2enmod ssl
apache2ctl restart
echo -e "/root/Desktop/piSociEty/config/./profile" >> ~/.bashrc
```