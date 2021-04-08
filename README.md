# vl53l1x_pico
micropython driver for the vl53l1x ToF sensor

Originally taken from the OpenMV project's vl53 driver located here: https://github.com/openmv/openmv/blob/master/scripts/libraries/vl53l1x.py and then modified (simple mods) to allow the VL53L1X sensor from pimoroni (maybe others) to be used on the Raspberry Pico. Note i didnt want to clone the whole library just for this as i'm still testing but it seems to work ok.

The following code reads the sensor and outputs the distance (tested using thonny)


~~~python

from machine import I2C
from vl53l1x import VL53L1X
import time
i2c = I2C(0)
distance = VL53L1X(i2c)
while True:
    print("range: mm ", distance.read())
    time.sleep_ms(50)

~~~
