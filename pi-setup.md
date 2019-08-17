# SFPC Detroit pi setup


## 1. **Within the initial setup interface**
- use Detroit timezone
- change pw to `morepoetry`
    - username remains `pi`
- join wifi
- say `Skip` to skip software updates 
- say `later` to restart later


## 2. **Manually on each pi**

*IMPORTANT* change `sfpc-x` to `sfpc-3 or 4 or 5 etc..` in the lines below

- `sudo nano /etc/hostname`
    - replace raspberrypi with `sfpc-x` 
    - save and close: `ctrl + x` + `y` + `enter`
- `sudo apt-get update`
- `sudo apt-get upgrade` (this takes a while)
    - `y`
- `sudo reboot` to restart
- open Chrome and navigate to this page: https://github.com/SFPC/detroit/edit/master/pi-setup.md
- `nano .bashrc`
    - append this line: `alias tree='find . -print | sed -e "s;[^/]*/;|**;g;s;**|; |;g"'`
    - save and close: `ctrl + x` + `y` + `enter`


## 3. **run this bash script all at once**

    sudo apt-get install avahi-daemon
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash  
    export NVM_DIR="$HOME/.config["[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
    source ~/.bashrc
    nvm install --lts
    nvm use --lts
    npm install -g dat
    mkdir folder-poetry


## 4. **Manually on each pi**

*IMPORTANT* change `sfpc-x` to `sfpc-3 or 4 or 5 etc..` in the line below
- `sudo nano /etc/hosts`
    - append this line (CHANGE sfpc-x to the correct number): `127.0.0.1       localhost localhost.localdomain.sfpc-x`
    
**Enable SSH**
- `sudo raspi-config`
- select: `Interfacing Options` > `SSH`, `turn SSH on`



### To SSH into an sfpc pi
`ssh pi@sfpc-2`



---

### Troubleshooting Display

When you plug in the Pi to monitor, with a HDMI cable, you may notice a black border around the image. This is because the operating system is not in HDMI mode yet. 

Now, open up the terminal, and go to the Boot folder.

`cd ..`

you will be at the /home

`cd ..` 

one more time and you will be at the root level. this is the top level in the SD card. 

now, we will go into the boot folder. 

`cd boot`

now, we are going to change 

`sudo nano config.txt`

uncomment (by removing #) 

`disable_overscan=1`

save and close: `ctrl + x` + `y` + `enter`



### Setup Continued

Get back to home directory

`cd`
- `cd` always brings you back to home from wherever you are in your folder tree.

Install git

`sudo apt install git`

Install python 3

`sudo apt-get install python3-picamera`

`sudo reboot`




----------------------------------

### Melanie's Notes, ignore

`sudo nano config.txt`

`sudo apt install git`

`sudo apt-get install python3-picamera`


