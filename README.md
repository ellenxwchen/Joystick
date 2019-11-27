# Joystick
Implementation of joystick 

Configuring PS2 Joystick 
http://wiki.ros.org/joy/Tutorials/ConfiguringALinuxJoystick

Installing the Package 
sudo apt-get install ros-kinetic-joy

Configuring the Joystick
ls /dev/input/ 
	should see jsX (X is a number, usually 0 - this is your joystick)
sudo jstest /dev/input/jsX
ls -l /dev/input/jsX
	if XX is rw: the js device is configured properly. 
	if XX is --: the js device is not configured properly and you need to: 
			sudo chmod a+rw /dev/input/js0

Starting the Joy Node
roscore
rosparam set joy_node/dev "/dev/input/jsX"
rosrun joy joy_node
In new terminal: rostopic echo joy
