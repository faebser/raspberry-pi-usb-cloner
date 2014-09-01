# raspberry pi usb-cake replicator

## sponsor

This project was made possible by the people at [Tweaklab](http://www.tweaklab.ch).

## installation

### simple

* ssh into your raspberry
* `git clone https://github.com/faebser/raspberry-pi-usb-cloner.git`
* make sure that cloner.py and usb.sh is executable
* `python cloner.py` to run the app
* navigate your browser to the ip of your raspi, the default port is 8080

### run on startup

* ssh into your raspberry
* `git clone https://github.com/faebser/raspberry-pi-usb-cloner.git`
* make sure that cloner.py and usb.sh is executable
* in the home directory create a file run.sh with the following content 
```bash
#!/bin/bash

for pid in $(pidof -x python cloner.py); do
        if [ $pid != $$ ]; then
                echo "[$(date)] : Cloner : Process is already running with PID $pid"
                exit 1
        fi
done

echo "starting cloner"

cd /DIR/TO/CLONER

while true
do
sh -c "python cloner.py"
sleep 3
done
```
* edit your .bashrc and add `./run.sh`
* reboot

## usage

## screenshots
