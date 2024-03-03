# LCD lesson

This repository is the starting stone to using Python, Orange Pi 3 LTS, LCD
Nokia 5110 and Jumper wires to display information.

## Hardware

- [Orange 3 LTS](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/orange-pi-3-LTS.html)
- [LCD Nokia 5110](https://components101.com/displays/nokia-5110-lcd)
- [Jumper Wires](https://en.wikipedia.org/wiki/Jump_wire)

## Dependencies

These libraries do not come with python out of the box
- wiringpi (follow [instruction](/install_wiring_pi.txt))
- spidev (`pip install spidev`)

## Background

#### SPI (Serial Peripheral Interface)

SPI (Serial Peripheral Interface) is a synchronous serial communication
protocol used for communicating between microcontrollers, sensors, memory
devices, and other peripherals in embedded systems. It typically involves a
master-slave configuration, where one device (the master) controls the
communication and initiates data transfers with one or more peripheral
devices (the slaves). In our case, the LCD Nokia 5110 uses SPI to
communicate with Orange Pi 3 LTS where Orange Pi 3 LTS serves as the
master and the LCD Nokia 5110 as the slave.

Devices that communicate via SPI need these connections:
- SCLK (Serial Clock): This line carries clock signals generated by the
  master to synchronize data transmission between the master and the slave.
- MOSI (Master Out Slave In): This line carries data from the master to the
  slave.
- MISO (Master In Slave Out): This line carries data from the slave to the
  master.
- SS/CS (Slave Select/Chip Select): This line is used by the master to
  select a specific slave device with which it wants to
  communicate. Typically, each slave device has its own SS/CS line.

#### Orange Pi pins

Pin layout corelation between Orange Pi pins (Hardware) labeled with H and
their functionality in Python code (wiringpi) labeled with W.

| H | W |   | W | H |
|---|---|---|---|---|
| 1 | 3v3 |   | 5v | 2 |
| 3 | w0 |   | 5v | 4 |
| 5 | w1 |   | GND | 6 |
| 7 | w2 |   | w3 | 8 |
| 9 | GND |   | w4 | 10 |
| 11 | w5 |   | w6 | 12 |
| 13 | w7 |   | GND | 14 |
| 15 | w8 |   | w9 | 16 |
| 17 | 3v3 |   | w10 | 18 |
| 19 | w11 |   | GND | 20 |
| 21 | w12 |   | w13 | 22 |
| 23 | w14 |   | w15 | 24 |
| 25 | GND |   | w16 | 26 |

#### LCD Nokia 5110 pins

| Number | Lable | Function |
|---|---|---|
| 1 | RST | Reset |
| 2 | CE | Chip Enable |
| 3 | D/C | Data/Command Selection |
| 4 | DIN | Serial Input |
| 5 | CLK | Clock Input |
| 6 | VCC | 3.3V |
| 7 | LIGHT | Backlight Control |
| 8 | GND | Ground |

## Demo 1 (only LCD)

This Demo focuses only on the LCD. Follow this [code](/lcd_sample_code.py)
to display a counter which increases every second.

#### Wiring

![wiring for demo 1](/assets/)

## Demo 2 (LCD + button)

This Demo focuses using the LCD in conjunction with other components like a
button. Follow this [code](/lcd_sample_code_button.py) to display whether
the button is pressed or not.

#### Wiring

![wiring for demo 2](/assets/)

## Common problems

Check your wiring.  Are the wires connected to the correct pins?  Are the
wires plugged in properly.

Check the brightness of the LCD.  You might need it to be brighter.

Have you downloaded all necessary dependencies?
