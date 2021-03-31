# BrewPiLess-32-PCB
PCB board to test BPL firmware from @vitotai with ESP32: https://github.com/vitotai/BrewPiLess

Support 3 versions of ESP32 Devkit
- 30 Pin
- 36 Pin
- 38 pin

Board Size: 80 x 100 mm

Layers: 2

![PCB Top](https://github.com/stefschin/BrewPiLess-32-PCB/blob/master/Top%20view%203D.JPG)

For connections see:

See https://github.com/vitotai/BrewPiLess/blob/master/doc/ESP32Pins.md

Free to download gerbers to build yourself or send to a PCB Manufacturer.

Purchase directly to PCBWay: https://www.pcbway.com/project/shareproject/BrewPiLess_ESP32_Rev_00.html

# Power Supply options
## External PS between 8-28Vdc

It uses an Input from 8-28 Vdc with a MP1584 Module.

IMPORTANT!!!! Don't populate JP1 jumper until you regulate this module output voltage.
Power on J1 with a voltage between 8 and 28 Vdc, be carefull about polarity.
Then regulate output to 5Vdc with potentiometer on module. 
After checked that voltage, you can populate Jumper to supply power to all board.

## External PS 5Vdc

If you want to supply this board with 5Vdc directly, don't use MP1584 module and instead solder a jumper cable between Vin+ and Vout+.
Power supply input on J1 too.

## USB PS to ESP32

You can supply 5V throught USB from ESP32 too, but you are limited to 500mA from a computer, and 1A from an external 5V power supply

# Features:
- 1 analog input for Sensor, like 5Vdc pressure sensor (P3), populate R4=10K and R5=20K to have a voltage divider of 1.5
- 3 digital input for Rotary Encoder or Switches (P6) 
- 2 extra Input/Outputs for sensores or 2-relay Module (P8)
- 4 Input/Outputs for 4-relay Module (P5)
- 1 output for buzzer module or you can populate R6=10K, Q1=2N7000/2N7002 Mosfet transistor channel N, BZ1=5Vdc buzzer - diam=12mm
- 1 UART0 comm port (P9), you can interface it with a USB/RS-232 TTL module to communicate with PC (3.3V compatible)
- 1 One Wire port, mostly for read temperature sensors like DS18B20, you can connect in parallel. Populate R1=4.7K for less than 3 sensors. 
- 1 extra Input/Outputs for sensores or 1-relay Module (P1)
- 1 OLED I2C connection for 4 or 7 pin 0.96 module (P4)
- 1 extra I2C port, for display LCD or ADC module ADS1115 (P11). You can select between 5 and 3.3V for this connector, soldering JP2 between 1-2 or 2-3 pins. Populate R2=4.7K and R3=4.7K if your I2C device doesn't have it. Oled/LCD and ADC module have it.
- 1 JTAG connection for debug with [ESP-Prog](https://www.amazon.com/ESP-Prog-Development-Program-Downloader-Compatible/dp/B07WGDJF61/)

