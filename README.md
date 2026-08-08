# Hamza Mohamed
# mechatronics engineering student at the Capital University.

## Tank Control System
Platform: CODESYS
Language: Ladder Logic 
Hardware: Simulated

## Brief Summary
A system that controls the Pump and Drain, The cycle begins when the operator press start where the liquid is on the bottom of the tank (Low level sensor is on) and the Pump will start with the Latching mechanism, after the tank is full the Pump automatically shuts down and after 5-sec delay the Drain Turns on until the liquid is drops below the Low level sensor and after 5-sec if the continue button is pressed the Pump is on for 2-sec to refill at the Low sensor and the cycle continues Automatically.

### The How
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
![Start Logic](Tank_Images/PumpandHighSensor.png)
*This two rungs represent the latch-in pump and the High level sensor indication.*

![Pump system](Tank_Images/PumpMechanism.png)
*this rung as all the Pump mechanism with the 2-sec refilling and the cycle confirmation.*

![Drain system](Tank_Images/Delay+Drain+LowSensor.png)
*This part has the Drain and also the Latch mechanism, with the 5-sec delay to let the liquid rest and the Low Level sensor*

![Variables](Tank_Images/Variables.png)
*These are all the variables in the system.*

## Skills Learned
-The Latching Mechanism, so that the operator doesn't have to hold the Same Button 

-The Three Types of Timer Blocks, controlling every action with precise sequence 
