# Hamza Mohamed

## mechatronics engineering student at the Capital University.

## Tank Control System V1

Platform: CODESYS

Language: Ladder Logic 

Hardware: Simulated

## Brief Summary
A system that controls the Pump and Drain, The cycle begins when the operator press start where the liquid is on the bottom of the tank (Low level sensor is on) and the Pump will start with the Latching mechanism, after the tank is full the Pump automatically shuts down and after 5-sec delay the Drain Turns on until the liquid is drops below the Low level sensor and after 5-sec if the continue button is pressed the Pump is on for 2-sec to refill at the Low sensor and the cycle continues Automatically.

### The Logic of the system
1.Press start => Pump starts
2.Tank is filled => Pump stops
3.After 5-sec delay => Drain starts
4.Tank is empty => Drains stops
5.Press confirm => Pump works only for 2-sec
6.Cycle repeats automatic from here

### I/O List

PROGRAM PLC_PRG
VAR
	START : BOOL;
	STOP : BOOL;
	HIGH : BOOL;
	LOW : BOOL := TRUE;
	PUMP : BOOL;
	DRAIN : BOOL;
	DELAY : TIME := T#5S;
	READY : BOOL;
	AGAIN : TIME := T#5S;
	CYCLE : BOOL;
	CONFIRMED : BOOL := TRUE;
	RETURN1 : TIME := T#2S;
END_VAR

### Screenshots Of the Project's LD
![Start Logic](Tank_Images/Pump_and_High_Sensor.png)
*This two rungs represent the latch-in pump and the High level sensor indication.*

![Pump system](Tank_Images/Pump_Mechanism.png)
*this rung as all the Pump mechanism with the 2-sec refilling and the cycle confirmation.*

![Drain system](Tank_Images/Delay+Drain+Low_Sensor.png)
*This part has the Drain and also the Latch mechanism, with the 5-sec delay to let the liquid rest and the Low Level sensor*

![Variables](Tank_Images/Variables.png)
*These are all the variables in the system.*

## Skills Learned
-The Latching Mechanism, so that the operator doesn't have to hold the Same Button 

-The Three Types of Timer Blocks, controlling every action with precise sequence 



# Tank System V2

Language : LD

Platform : CODESYS

Hardware : Simulated

## Brief Summary

In this version i learned the prefix for the variables to make sure that it's readable and made it automatic with a reset feature and for safety measures an automatic emergency stop is activated if the operator pressed the start button for more than 10-sec, by making automatic meaning that the full and empty sensor is activated when the pump/drain is on for about 5-sec (can be changed it is just for simulation) and by that the operator doesn't have to activate the full and empty sensor and if there is any malfunction the operator can press the stop and reset button but it wont affect the full/empty sensors just in real life industries and the reset button resets the cycle counter.

I/O List

HMI_START_BUTTON : BOOL;

HMI_STOP_BUTTON : BOOL;
HMI_RESET_BUTTON : BOOL;
IO_FULL_SENSOR : BOOL;
IO_EMPTY_SENSOR : BOOL;
IO_PUMP_OUTPUT : BOOL;
IO_DRAIN_OUTPUT : BOOL;
PLC_EMERGENCY_STOP : BOOL;
CFG_FILL_DELAY : TIME := T#5S;
CFG_SETTLE_DELAY : TIME:= T#5S;
CFG_EMPTY_DELAY : TIME := T#5S;
CFG_HOLD_START : TIME := T#7.5S;
CFG_WARNING_DELAY : TIME := T#2.5S;
CFG_BREAK_DELAY : TIME := T#3S;

## Screenshots of the project

