# Generate High-Frequency PWM with 2-Channel PWM 
The HS2070 is a 2-channel variable frequency /  variable duty cycle, PWM module for use as a square / rectangular wave generator. This unit is intended for use with DC brush motor controller or stepper motor driver.
#### Raspberry Pi
If you want to use this module with Raspberry Pi, you will need a level shifter because the voltage of Raspberry Pi pins is 3.3 volts, while the module requires 5 volts.

#### Arduino
To start working with this module, you need to connect it to a 5V power supply. You can use the Arduino pins to provide a 5V power supply by connecting Vin+ to 5 volts and Vin- to ground. Alternatively, you can connect a module to a 5V power supply using a micro-USB cable. The first way is easier and cheaper, in my opinion.

After that, you need to connect tx0 and rx0 of Arduino to txd and rxd of the module, and connect the ground of the module to one of the Arduino ground pins.

According to the datasheet, we have the following options for setting the PWM frequency:
###### Set The PWM Frequency
&nbsp;&nbsp;1)"S1FXXXT":setting PWM1 frequency of XXX HZ (001 ~ 999)
&nbsp;&nbsp;2)"S1FXX.XT":set the frequency of PWM1 XX.X KHZ (00.1 ~ 99.9)
&nbsp;&nbsp;3)"S1F:X.X.X.T":setting PWM1 frequency of XXX KHZ (0.0.1 ~ 1.5.0..)
&nbsp;&nbsp;4)'S1':PWM1
&nbsp;&nbsp;5)'S2':PWM2
&nbsp;&nbsp;6)'F':Frequency
&nbsp;&nbsp;7)'D':Duty Cycle
&nbsp;&nbsp;8)'T'is the end flag
###### Set The PWM Duty Cycle
&nbsp;&nbsp;1)"S1DXXXT":setting PWM1 duty cycle XXX;(001-100)
&nbsp;&nbsp;2)"S2DXXXT":set PWM2 duty cycle XXX;(001-100)
&nbsp;&nbsp;3)Setting Successful Return:DOWN
&nbsp;&nbsp;4)Setting Failback:FALL
