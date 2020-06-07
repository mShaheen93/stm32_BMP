Git clone libopen cm

Git clone Black Magic Probe


Install python

install python pip

install dfu-util    using usb cdc (Bootloader)  Flash using Bootloader

stm32   to flash using USB (TX,RX)



move libopencm inside blackmagic probe


inside black magic probe
    make PROBE_HOST=stlink
        will compile & provide elf&hex
        2 imp files   ( blackmagic_dfu.bin  & blackmagic.bin)
        blackmagic_dfu.bin  uses normal USB Port
