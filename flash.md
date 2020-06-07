# Flash Using USB to UART Conv

1. Connect TX & RX
2. Connect 3.3V & GND
    

        Boot 0 Jumper
    
        Change jumper from 0 to 1

3. inside blackmagic folder type the following command
    >stm32loader -p /dev/ttyUSB0 -e -w -v ./src/blackmagic_dfu.bin

    After Flashing Successfully

    try:
    >lsusb

    to check & see if we have **OpenMoko, Inc** Listed with USB ID **1d50:6017**

        Boot 0 Jumper
    
        Change jumper from 1 to 0

    #### **NOW we have the BMP Bootloader, NO NEED TO USE USB to UART anymore**

4. inside blackmagic folder type the following command
    >sudo dfu-util -d 1d50:6017 -s 0x8002000:leave -D ./src/blackmagic.bin

    >ls /dev/ttyACM*

    First Port is BMP Port which is used for debugging

    UART Emulator which is used for reading from the other COntroller (the one we will debug) UART to read the required data




# Flash using BMP as SWD

|BMP| Function|
|---|-------|
|GND|GND|
|PB14|SWD|
|PA05|SWCK|
|3.3V|3.3V|
|PA13|RX|
|PA14|TX|





# Flash using Arduino & FTDI

https://circuitdigest.com/microcontroller-projects/getting-started-with-stm32-development-board-stm32f103c8-using-arduino-ide



Board: Generic STM32F103C
Upload Method: Serial


## Code

    /*
    Blink
    Turns on an LED on for one second, then off for one second, repeatedly.

    Most Arduinos have an on-board LED you can control. On the Uno and
    Leonardo, it is attached to digital pin 13. If you're unsure what
    pin the on-board LED is connected to on your Arduino model, check
    the documentation at http://arduino.cc

    This example code is in the public domain.

    modified 8 May 2014
    by Scott Fitzgerald
    
    Modified by Roger Clark. www.rogerclark.net for Maple mini 25th April 2015 , where the LED is on PB1
    
    */

    # define led PC13

    // the setup function runs once when you press reset or power the board
    void setup() {
    // initialize digital pin PB1 as an output.
    pinMode(led, OUTPUT);
    }

    // the loop function runs over and over again forever
    void loop() {
    digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
    delay(1000);              // wait for a second
    digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
    delay(1000);              // wait for a second
    }



# Pinout

![STM32 Pinout](/img/pinout.png)