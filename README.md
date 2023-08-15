# Line Follower

This repository contains the Arduino code for controlling a robot using infrared (IR) sensors. The code enables the robot to navigate its environment based on input from the IR sensors, allowing it to avoid obstacles and make decisions about its movement. Below is an overview of the code structure and functionality.

## Hardware Configuration

The code is designed to control a robot with the following hardware components:

- 2 DC motors (left and right)
- 2 IR sensors (ir1, ir2) on the left side
- 3 IR sensors (ir3, ir4, ir5) on the right side
- Motor driver pins (lm1, lm2, rm1, rm2) for controlling the motors
- Enable pins (enl, enr) for motor speed control

## Setup

The `setup()` function is responsible for configuring the pins as inputs (IR sensors) and outputs (motor control pins) during the initialization of the Arduino board.

## Loop

The `loop()` function is the main part of the code that runs repeatedly. It reads the status of the IR sensors and uses their values to make decisions about the robot's movement.

## IR Sensor Logic

The IR sensors are used to detect obstacles and determine the robot's position relative to its surroundings. The code uses the readings from these sensors to identify different scenarios, such as encountering obstacles or following a path.

The following scenarios are considered:

- 11011: The robot moves forward when detecting an obstacle on the left side.
- 11111: The robot moves backward when all sensors detect obstacles.
- 00011: The robot moves forward briefly and checks for a potential obstacle on the left side.
- 11000: The robot turns right when the rightmost sensors detect an obstacle.
- 00000: The robot turns right when all sensors detect no obstacles.
- 11001: The robot turns right when the obstacle is detected in front and on the left side.
- 10011: The robot turns left when the obstacle is detected in front and on the right side.
- 11101: The robot turns right when the obstacle is detected on the right side.
- 10111: The robot turns left when the obstacle is detected on the left side.
- 11100: The robot turns right when obstacles are detected on the sides and in front on the right.
- 00111: The robot turns left when obstacles are detected on the sides and in front on the left.

## Movement Functions

The code includes movement functions for controlling the robot's motion:

- `forward()`: Moves the robot forward.
- `STOP()`: Stops the robot's motion.
- `right()`: Turns the robot to the right.
- `left()`: Turns the robot to the left.
- `back()`: Moves the robot backward.

## Motor Speed Control

The `analogWrite()` function is used to control the speed of the robot's motors. The values provided to this function determine the PWM duty cycle and, consequently, the speed of the motors.

## Usage

To use this code, follow these steps:

1. Set up the hardware components as described in the "Hardware Configuration" section.
2. Upload the provided code to your Arduino board.
3. Connect the Arduino board to the robot.
4. Power on the robot and observe its behavior as it navigates based on the IR sensor readings.

**Happy Robotics!**

<img width="505" alt="line" src="https://github.com/Kushal-Pareek/Line-follower/assets/88341691/7840e884-3abf-4573-87a8-442ce709057d">
