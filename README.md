# setup raspberry pi without screen and keyboard

install os in memory card  
insert memory cary in laptop -> open boot partition

---

### to enale ssh
make empty file named ssh  
$touch ssh

---

### to make user
make file named userconf.txt  
$nano userconf.txt

add username and password in file in this formate  
username:encrypted-password

to get encrypted password:  
$echo 'mypassword' | openssl passwd -6 -stdin

---

### to setup wifi
make file named wpa_supplicant.conf  
add following details in that file

country=IN  
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev  
update_config=1  

network={  
    scan_ssid=1  
    ssid="wifi name/ssid"  
    psk="password"  
}

---

**insert memory card into raspberry pi and power it up**

---

### to connect pi from ssh
download net analyzer app in phone  
scan LAN devices  
there will be ip with name raspberry (wait up to 5 min or booting up raspberry)  
then connect ssh to that ip and username we set in above steps  
(make sure laptop is also connected to same network)  

$ssh username@ip  
password  

---

### make python virtual environment
$pip3 install virtualenv virtualenvwrapper  
$nano ~/.bashrc  

**add following lines at end of file**  

export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3  
export WORKON_HOME=$HOME/.virtualenvs  
export VIRTUALENVWRAPPER_VIRTUALENV=~/.local/bin/virtualenv  
source ~/.local/bin/virtualenvwrapper.sh  
export VIRTUALENVWRAPPER_ENV_BIN_DIR=bin  

$source ~/.bashrc

**make vietual env**  
$mkvirtualenv -p python3.8 envname

**to activate env**  
$workon main

[**raspberry pi reference**] (https://raspberrypi-guide.github.io/programming/create-python-virtual-environment)  
[**python virtual wrapper reference**] (https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html)

---

### run yolo


---

enjoy!!!
