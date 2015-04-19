# Readme: ambihue

Python script to intgrate Philips Hue lights with Philips Ambilight TV's for a room wide Ambilight effect.

## Installation

```
emerge -av simplejson # for python 2.x
pip2 install phue
```

### systemd integration

```
cp systemd/user/ambihue.service ~/.config/systemd/user/
# adjust path and restart time in the service-file
systemctl --user enable ambihue
systemctl --user start ambihue
```

## Configuration

- Configure IP adress of Ambilight TV
- Configure IP adress of HUE bridge
- Attach HUE lights to zones of the Ambilight TV
- The HUE light nr's can be found in the official HUE app

## Running (without systemd)

- Press the connect button of the Hue bridge (only the first time you run this script)
run 
```
python2 ambihue.py
```

