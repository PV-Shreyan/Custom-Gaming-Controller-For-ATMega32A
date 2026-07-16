# Custom-Gaming-Controller-For-ATMega32A
This is a fun little low-cost project I made using the micro-controller ATMega32A to create a custom gaming controller to play virtually any game possible. The whole cost of this project was just under 8 US dollars for me and its pretty fast, responsive and customizable with room to include custom buttons for your purpose, so have some fun gamers :)

For this Project, I'll go over step-by-step on what you need to do to get this thing working.

---
# What you need:
* First an formost an IDE to code. I used Microchip Studio, you can use any IDE you like.
* Second, a flasher to flash you code onto the MCU (Microcontroller). I used WinAVRFlasher, you can use any other flasher you like.
* Sadly, this is not a simple plug and play thing as this MCU lacks the native USB support for it so you'll need to download and use these three programs for now:

[vJoySerialFeeder](https://github.com/Cleric-K/vJoySerialFeeder) (v1.7.1)\
[HidHide configuration client](https://github.com/nefarius/HidHide) (v1.5.230.0)\
[XOutput](https://github.com/csutorasa/XOutput) (v3.31)

### Now to the fun part. Buying the components:
```text
1 ATMega32A MCU
1 USB/ASP Programmer
1 UART-to-USB Converter (featuring CP2102 UART-to-TTL serial chip)
2 standard PS2 joysticks (5 pins)
16 push buttons
2 standard breadboards (16.5cm x 5.5cm) or 1 big breadboard of your choice or a solder board to 
handful of male-to-male jumper cables and a few female-to-female and a few male-to-female jumper cables
few 10k ohm resistors, 2 100nF capacitors, 1 10uH inductor
```
# Hardware Configuration:
* I've written the code in the button format of an XBOX controller. You can change the format to your liking if you wish to do so.
<br><br/>
<img width="988" height="516" alt="image" src="https://github.com/user-attachments/assets/91e9e2f2-ec28-488e-8f93-de25c0ec8dcd" />
<br><br/>

* Now that we have all the necessary components and softwares. The only thing left to do is to actually wire the hardware. Take the below image as reference for wiring your controller.
<br><br/>
* If you are following the connections on the image exactly as is then you can use the code as it is but if you aren't then comment the original keypad block and uncomment the block under it.
<br><br/>
<img width="1141" height="805" alt="image" src="https://github.com/user-attachments/assets/a1d65bad-0c52-42e3-9440-9a44a8fe6dbf" />
<br><br/>

* Quickly note that the X-axis and Y-axis of the analog stick should be connected to the LS-X1, LS-Y1 and RS-X2, RS-Y2 respectively. The L3 and R3 pins should be connected to the button pin (SW) of the analog stick.

# Flashing the MCU:
* Now, I hope that you are all set up and ready to go. Because all you need to do now is to build your project to create a hex file and flash the MCU.
But before we do that, grab your USB/ASP Programmer and connect it to your MCU as per the below image while keeping the small notch as a point of reference.
<br><br/>
<img width="895" height="739" alt="image" src="https://github.com/user-attachments/assets/854bee9a-1abd-43cf-b5e4-272b0b29651c" />
<br><br/>

* Now that you have successfully connected the Programmer, we can proceed to the flashing part. Note that these should be your settings if you are using WinAVRFlasher. 
<br><br/>
<img width="1207" height="688" alt="image" src="https://github.com/user-attachments/assets/be28c06f-f76d-4634-bbe3-db5a9788f9e0" />

### BEWARE!! Make sure you carefully select the correct settings shown otherwise you CAN brick your controller. Proceed with CAUTION!! 
You can safely ignore the baud rate and port settings in WinAVRFlasher.
Be sure to select the proper hex file path.
That's it, now you can flash you MCU safely.
<br><br/>
After Flashing the MCU, you can disconnect the programmer from your PC and remove the connections for it on your MCU. The UART-to-TTL converter you got will be the one powering the MCU and communicating with your PC.
<br><br/>
For the UART-to-TTL converter, you should connect the Tx and Rx pins in a criss-crossed manner to the MCU and power the Converter with direct 5V from the MCU and connect its ground pin to a common ground with the MCU. This is __NECESSARY!!__

# Configuring vJoySerialFeeder:
* Note that the ATMega32A does not have native USB support, so when we use a UART-to-TTL converter, the connection will appear as a standard COM device. This type of connection will be useless as games don't read COM devices, they expect a HID devices __(Human Interface Device)__
* This is why we will use vJoySerialFeeder which will configure our COM port as a HID port.

| Feature | Specification | 
| --- | --- |
| Baudrate | 250000 |
| Latency | 5-6ms |
| Programmable Buttons | 4 |
| ADC Resolution | 10-bit |
|  |  |
