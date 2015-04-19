# Readme: ambihue
Python script to intgrate Philips Hue lights with Philips Ambilight TVs for a room wide Ambilight effect.

## Installation
Install simplejson:
```.sh
emerge -av simplejson          # for Gentoo (python2_7-target must be set)
pacman -S python2-simplejson   # for Arch or
yum install python-simplejson  # for Fedora (python2 only)
```

Make sure you have pip installed and use it to get the latest version of phue:
```.sh
pip2 install phue              # all distributions
```

### systemd integration
To never manually restart the script you can integrate it with systemd. systemd detects when the script exits because it lost connection to the TV or bridge and restarts it after a configured time period.
```.sh
cp systemd/user/ambihue.service ~/.config/systemd/user/
    # adjust path and restart-time in the service-file
systemctl --user enable ambihue
systemctl --user start ambihue
```

Note, that you need to press the bridge-button before the first start of ambihue, regardless wether you want to integrate it with systemd.

## Configuration
Configuration can be done in the first lines of the ambihue-script itself:
- Configure IP adress of Ambilight TV
- Configure IP adress of HUE bridge
- assign HUE light numbers to zones of the Ambilight TV

## Running for the first time (or without systemd)
- Press the connect button of the Hue bridge (only the first time you run this script)
run 
```.sh
python2 ambihue.py
```

