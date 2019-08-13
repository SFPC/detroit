# SFPC Detroit pi setup

## 1. **Within the initial setup interface**
- use Detroit timezone
- change pw to `morepoetry`
    - username remains `pi`
- Say `Skip` to skip software updates 
- say `later` to restart later


## 2. **Manually on each pi**

*IMPORTANT* change `sfpc-x` to `sfpc-3 or 4 or 5 etc..` in the lines below

- `sudo nano /etc/hostname`
    - replace raspberrypi with `sfpc-x` 
    - save and close: `ctrl + x` + `y` + `enter`
- `nano .bashrc`
    - append this line: `alias tree='find . -print | sed -e "s;[^/]*/;|**;g;s;**|; |;g"'`
    - save and close: `ctrl + x` + `y` + `enter`
- `sudo apt-get update`
- `sudo apt-get upgrade`
    - `y`
- `sudo reboot` to restart
- open Chrome and navigate to this page: https://github.com/SFPC/detroit/edit/master/pi-setup.md


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
`sudo raspi-config`

select: `Interfacing Options` > `SSH`, `turn SSH on`



### *To SSH into an sfpc pi:**
`ssh pi@sfpc-2`
