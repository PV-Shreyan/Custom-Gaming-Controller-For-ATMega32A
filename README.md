# Custom-Gaming-Controller-For-ATMega32A
This is a fun little project I made using the micro-controller ATMega32A to create a custom gaming controller to play virtually any game. The whole cost of this project was just under 8 US dollars for me and its pretty fast, responsive and customizable with room to include custom buttons for your purpose, so have some fun gamers :P

What you need:
1. First an formost an IDE to code. I used Microchip Studio, you can use any IDE you like.
2. Second, a flasher to flash you code onto the MCU. I used WinAVRFlasher, you can use any other flasher you like.
3. Sadly, this is not a simple plug and play thing as this MCU lacks the native USB support for it so you'll need to download these three programs for now: "vJoySerialFeeder" (v1.7.1), "HidHide configuration client" (v1.5.230.0) and "XOutput" (v3.31)

4. Now to the fun part. The components:
   1 ATMega32A MCU
   1 USB/ASP Programmer
   1 UART-to-USB Converter (featuring CP2102 UART-to-TTL serial chip)
   2 standard PS2 joysticks
   16 push buttons
   
