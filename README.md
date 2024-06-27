## BEFORE YOU PROCEED

- ##### MPU6050 is old, noisy and the documentation SUCKS, go for other IMUs. If you have a MPU6050 lying and just wanna tinker with it, then fine.

- ##### This is a very simple implementation of fall detection and you would need to use Kalman filters and stuff to make it more accurate. It does not make sense to do that much on an MPU6050. Again, just go for another IMU if possible.


## UNDERSTANDING THE REGISTERS

- The two registers, FF_THR (0x1D) AND FF_DUR (0X1E) can be used to set the acceleration threshold and duration to trigger an interrupt.
- The two registers, FF_THR (0x1D) AND FF_DUR (0X1E) which can be used to set the acceleration threshold and duration to trigger an interrupt.
- For the FF_THR, 1LSB=2mg and it increments the FF_DUR (1LSB=1ms) by 1 if the acceleration value in each one of the axis is less than the threshold value and it decrements the FF_DUR if it is above the threshold value. When the time crosses the FF_DUR value, it triggers an interrupt.
- To enable the free fall interrupt we must set the 7th bit of INT_ENABLE (0x38) to 1 and the status of free fall interrupt can be read from the 7th bit of INT_STATUS (0x3A).
- Perform bitwise manipulation of the rgisters rather than wrting an 8 bit data directly (you can do it but only if you are sure about all the other 7 bits.)

#### [Here is the register map](https://www.i2cdevlib.com/devices/mpu6050#registers) 
