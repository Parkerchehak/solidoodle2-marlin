#Marlin firmware for Solidoodle 2

Previous official Solidoodle firmware was based on early version of Marlin and could not be altered to accomodate a Panelolu LCD screen and encoder without many errors. This version has configuration.h and configuration_adv.h altered to reflect all changes found in official Solidoodle firmware.

Instructions:

1.  You need to have the Arduino0022 IDE installed. If you have a later version, you'll need to downgrade.

PC Users: A version of Arduino022 already setup for this firmware is now available in the download section. Simply unzip into a folder of your choice.
Skip to step 4.

MAC Users: Download from:

-http://arduino.cc/hu/Main/Software


2.  (Mac only) Clone the repository at

-https://github.com/jmgiacalone/sanguino1284p

and copy the included Sanguino directory to the hardware directory of your Arduino install. On Mac OS X, that would be ~/Documents/Arduino/hardware.

3.  (Mac Only) Close the Arduino IDE and then copy the file avrdude.conf from the sanguino1284p clone to your ~/Documents/Arduino/hardware/tools/avr/etc.

Start the Arduino IDE and you should now see 'Sanguino W/ ATmega644P' AND 'Sanguino W/ ATmega1284P' options in the Tools->Board menu.

4.  For the standard Solidoodle 2 model with the 644P microcontroller, upload the firmware as is and select the 'Sanguino W/ ATmega644P' option.

5.  If you're adding an SDSL SDCARD reader, or Panelolu LCD display and rotary encoder with SDSL, you will need to select the 'Sanguino W/ ATmega1284P' board. Please purchase a 1284P with a bootloader already in place.

For a Panelolu/SD card reader combo, uncomment line 302 in configuration.h from:

```C
//#define ULTIPANEL
```
to:
```C
#define ULTIPANEL
```
Now compile and upload.

-http://www.soliforum.com/topic/127/panelolu-complete-guide/
-http://www.emakershop.com/browse/listing?l=280
-http://www.emakershop.com/browse/listing?l=307
-http://blog.think3dprint3d.com/2012/06/panelolu-in-depth.html


If you're only adding SDSL, uncomment line 290 in configuration.h from:
```C
//#define SDSUPPORT // Enable SD Card Support in Hardware Console
```
to:
```C
#define SDSUPPORT // Enable SD Card Support in Hardware Console
```
Now compile and upload.

-http://reprap.org/wiki/SDSL
-http://www.emakershop.com/browse/listing?l=182

See instructions above for wiring.




