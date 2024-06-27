##BEFORE YOU PROCEED

- #####MPU6050 is old,noisy and the documentation SUCKS,go for other IMUs.If you have a MPU6050 lying and just wanna tinker with it,then fine.

##UNDERSTANDING THE REGISTERS
- For simple fall detection(without using Kalman Filter and stuff) we have two registers, FF_THR (0x1D) AND FF_DUR (0X1E) which can be used to set the acceleration threshold and duration to trigger an interrupt.
- To enable the free fall interrupt we must set the 7th bit of INT_ENABLE (0x38) to 1 and the status of free fall interrupt can be read from the 7th bit of INT_STATUS (0x3A).
- Perform bitwise manipulation of the rgisters rather than wrting an 8 bit data directly (you can do it but only if you are sure about all the other 7 bits.)
- Support TeX (LaTeX expressions, Based on KaTeX), Flowchart and Sequence Diagram of Markdown extended syntax;
- Support AMD/CMD (Require.js & Sea.js) Module Loader, and Custom/define editor plugins;

####[Here is the register map](https://www.i2cdevlib.com/devices/mpu6050#registers) 

