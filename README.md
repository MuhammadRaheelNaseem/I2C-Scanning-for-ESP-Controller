# I2C-Scanning-for-ESP-Controller

```python
from machine import Pin, I2C

# I2C configuration for ESP32
i2c = I2C(0, scl=Pin(22), sda=Pin(21), freq=400000)  

def scan_i2c(i2c):
    devices = i2c.scan()
    print("Device Name: ",devices)
    if devices:
        print('I2C devices found:', len(devices))
        for device in devices:
            print('I2C address: {}'.format(hex(device)))
    else:
        print('No I2C devices found')

scan_i2c(i2c)

```
