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
- `sudo apt-get update`
- `sudo apt-get upgrade`
    - `y`
- `sudo reboot` to restart
- open Chrome and navigate to this page: https://github.com/SFPC/detroit/edit/master/pi-setup.md


## 3. **run this bash script all at once**

    sudo apt-get install avahi-daemon
    curl -o- [https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh](https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh) | bash
    export NVM_DIR="$HOME/.config"[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" # This loads nvm bash_completion
    source ~/.bashrc
    nvm install --lts
    nvm use --lts
    npm install -g dat
    mkdir folder-poetry
    echo 'alias tree="find . -print | sed -e 's;[^/]*/;|**;g;s;**|; |;g'"' >> ~/.bashrc


## 4. **Manually on each pi**

*IMPORTANT* change `sfpc-x` to `sfpc-3 or 4 or 5 etc..` in the line below

- `sudo echo '127.0.0.1       localhost localhost.localdomain.sfpc-x' >> /etc/hosts`
- `curl -O "[http://aoakley.com/articles/raspbian-image-enable-ssh](http://aoakley.com/articles/raspbian-image-enable-ssh)" && sudo mv raspbian-image-enable-ssh /usr/local/sbin && sudo chmod 755 /usr/local/sbin/raspbian-image-enable-ssh && sudo chown root.root /usr/local/sbin/raspbian-image-enable-ssh`



### *To SSH into an sfpc pi:**
`ssh pi@sfpc-2`
