# waveshare-epaper

The WaveShare epaper module (B) handles 3 colours, black, white and red.
A link is listed below

https://www.waveshare.com/wiki/1.54inch_e-Paper_Module_(B)#Enable_SPI_interface


The actual module is from the following link

https://www.jaycar.com.au/duinotech-1-54-inch-monochrome-e-ink-display-module/p/XC3747


For the Arduino, the following repository was used

https://github.com/soonuse/epd-library-arduino

For the raspberry pi, the following repository was used,

https://github.com/soonuse/epd-library-wiringpi



# Installation
Ensure raspbian-lite is installed
```bash
$ sudo apt-get update; sudo apt-get upgrade
```


Ensure to run
```bash
$ sudo raspi-config
```
And enable SPI, and reboot the machine.

Install BCM2835 libraries
```
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.60.tar.gz
tar zxvf bcm2835-1.60.tar.gz 
cd bcm2835-1.60/
sudo ./configure
sudo make
sudo make check
sudo make install
#For more details, please refer to http://www.airspayce.com/mikem/bcm2835/
```
    Install wiringPi libraries
```
sudo apt-get install wiringpi

#For Pi 4, you need to update it：
cd /tmp
wget https://project-downloads.drogon.net/wiringpi-latest.deb
sudo dpkg -i wiringpi-latest.deb
gpio -v
```

Install Python libraries
Install Python3
```bash
$ sudo apt-get update
$ sudo apt-get install python3-pip
$ sudo apt-get install python3-pil
$ sudo apt-get install python3-numpy
$ sudo pip3 install RPi.GPIO
$ sudo pip3 install spidev
```
## Examples
Open terminal and execute command to download demo codes
```bash
sudo git clone https://github.com/waveshare/e-Paper
cd e-Paper/RaspberryPi\&JetsonNano/
```
Running examples

### C codes

Find the main.c file, uncomment the definition of e-Paper types, then compile and run the codes.
```bash
cd c
make clean
make
sudo ./epd
```

### python

Run examples, xxx is the name of the e-Paper. For example, if you want to run codes of 1.54inch e-Paper Module, you xxx should be epd_1in54
```bash
cd python/examples
# python2
sudo python xxx.py
# python3
sudo python3 xxx.py
```
