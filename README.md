# RPI_SGP30

Based on the smbus2 for ease of use. Program to read eCO_2 and TVOC from the [SGP30 sensor](https://www.sensirion.com/fileadmin/user_upload/customers/sensirion/Dokumente/9_Gas_Sensors/Sensirion_Gas_Sensors_SGP30_Datasheet_EN.pdf).

It currently lacks support for many features features and is more of a crude demo than a proper library.

## Features that are known to be missing (listing in rough order of importance):
* CRC support
* reading/writing base-line data
* reading raw-values
* Proper structuring of the code

If you have the AdaFruit board with built in level shifters and voltage regulator it is should work if you just plug in [SDA to pin 3, SCL to pin 5, VCC to pin 17 and GND to pin 20](https://pinout.xyz/pinout/i2c). You should then be able to find the SGP30 an address 0x58 using `i2cdetect -y 1`. If you get an error message  you probbably need to enable i2c in the kernel using  [`raspi-config` and reboot](https://learn.sparkfun.com/tutorials/raspberry-pi-spi-and-i2c-tutorial)
