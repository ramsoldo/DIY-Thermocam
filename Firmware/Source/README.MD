# DIY-Thermocam Firmware Development #

GNU General Public License v3.0
Copyright by Max Ritter


<img src="https://github.com/maxritter/DIY-Thermocam/raw/master/Images/Website/Diagram.png" width="500">

**THIS GUIDE IS ONLY REQUIRED, IF YOU WANT TO MAKE CHANGES TO THE FIRMWARE ON YOUR OWN!**

If you just want to flash the newest version of the firmware to your device, follow the Firmware Update Guide in the Document section and use one of the pre-compiled versions (*.hex) from **[here](https://github.com/maxritter/DIY-Thermocam/tree/master/Firmware/Releases)**.


Download and install the following programs:

1. Arduino 1.8.4+:                      https://www.arduino.cc/en/Main/Software
2. Teensyduino 1.39+:                   https://www.pjrc.com/teensy/td_download.html
3. Visual Studio 2015/2017 Community:  https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx
4. Visual Micro:                       http://www.visualmicro.com/page/Arduino-Visual-Studio-Downloads.aspx

If you are using the DIY-Thermocam V1 with the Teensy 3.2, you need to unlock the overclock option first. Go to the Teensy avr folder (f.ex. "C:\Program Files (x86)\Arduino\hardware\teensy\avr\"), open the file "boards.txt" and remove the hash (#) symbol in front of this line: "teensy31.menu.speed.144=144 MHz (overclock)", then save the file.

Now Start Visual Studio.

Go to Tools -> VisualMicro -> Configure Ide Locations. 
Set the ide folder location of your Arduino installation (f.ex. "C:\Program Files (x86)\Arduino") and the optional sketchbook location to this project (f.ex. "C:\Dev\VisualMicro\DIY-Thermocam\").

In the "vMicro" menu, select the following settings:

For DIY-Thermocam V1:
IDE: Arduino 1.6; 
Board: Teensy 3.1/3.2; 
Option1: USB Type: Serial; 
Option2: CPU Speed 144MHz;
Option3: Optimize: Faster

For DIY-Thermocam V2:
IDE: Arduino 1.6; 
Board: Teensy 3.6; 
Option1: USB Type: Serial; 
Option2: CPU Speed 240MHz;
Option3: Optimize: Fastest

Finally, select the right Comport from the list. 
If there is no Comport, upload a blank sketch with the USB Type "Serial" to the Arduino first over the Arduino IDE.

Open the project with Open -> Arduino Project and select the "DIY-Thermocam.ino". 

Compile the project with F7 or upload it directly to the Thermocam with F5.

If you are using the DIY-Thermocam V1 with the Teensy 3.2, you also need to include the mass storage part into your hex file. Copy the output hex "DIY-Thermocam.ino.hex" from Visual studio into the folder "MSD" and start the file "Unify.bat". A new file called "Firmware.hex" will be created.

Upload this file to your DIY-Thermocam with the teensy.exe uploader together with the teensy_reboot.exe from the "MSD" folder.
