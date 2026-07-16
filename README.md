# Custom-Gaming-Controller-For-ATMega32A
This is a fun little low-cost project I made using the micro-controller ATMega32A to create a custom gaming controller to play virtually any game possible. The whole cost of this project was just under 8 US dollars for me and its pretty fast, responsive and customizable with room to include custom buttons for your purpose, so have some fun gamers :P

For this Project, I'll go over step-by-step on what you need to do to get this thing working.

---
# What you need:
1. First an formost an IDE to code. I used Microchip Studio, you can use any IDE you like.
2. Second, a flasher to flash you code onto the MCU (Microcontroller). I used WinAVRFlasher, you can use any other flasher you like.
3. Sadly, this is not a simple plug and play thing as this MCU lacks the native USB support for it so you'll need to download these three programs for now:

[vJoySerialFeeder](https://github.com/Cleric-K/vJoySerialFeeder) (v1.7.1)\
[HidHide configuration client](https://github.com/nefarius/HidHide) (v1.5.230.0)\
[XOutput](https://github.com/csutorasa/XOutput) (v3.31)

### 4. Now to the fun part. Buying the components:
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

Now that we have all the necessary components and softwares. The only thing left to do is to actually wire the hardware. Take the below image as reference for wiring your controller.

<img width="1141" height="805" alt="image" src="https://github.com/user-attachments/assets/a1d65bad-0c52-42e3-9440-9a44a8fe6dbf" />

If you are following the connections on the image exactly then you can run the code as is but if you aren't then comment the original  

| Feature | Specification | 
| --- | --- |
| Baudrate | 250000 |
| Latency | 5-6ms |
|  |  |

