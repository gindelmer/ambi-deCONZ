# Readme: ambi-deCONZ
Python3 script to intgrate Zigbee lights (over [deCONZ](https://github.com/dresden-elektronik/deconz-rest-plugin)) with Philips Ambilight TVs for a room wide Ambilight effect.

## Installation
Install simplejson and urllib3:
```.sh
yum install python3-simplejson python3-urllib3 # for Fedora
apt install python3-simplejson python3-urllib3 # for Debian/Ubuntu
```

Make sure you have pip3 installed and use it to get the latest version of phue und pydeconz:
```.sh
pip3 install pydeconz phue # all distributions
```

### systemd integration
To never manually restart the script you can integrate it with systemd. systemd detects when the script exits because it lost connection to the TV or bridge and restarts it after a configured time period.
```.sh
cp systemd/user/ambi-deCONZ.service ~/.config/systemd/user/
    # adjust path and restart-time in the service-file
systemctl --user enable ambi-deCONZ
systemctl --user start ambi-deCONZ
```

Note, that you need to press the [Authenticate app](https://phoscon.de/en/app/doc#settings-gateway-advanced-en) button before the first start of ambi-deCONZ, regardless wether you want to integrate it with systemd.

## Configuration
Configuration can be done in the first lines of the ambi-deCONZ-script itself:
- Configure IP adress of Ambilight TV
- Configure IP adress and port of deCONZ app
- assign light numbers to zones of the Ambilight TV

## Running for the first time (or without systemd)
- Press the `authenticate app` button in the [Phoscon App](https://phoscon.de/en/app/doc#settings-gateway-advanced-en) (only the first time you run this script)
run
```.sh
python3 ambi-deCONZ.py
```
