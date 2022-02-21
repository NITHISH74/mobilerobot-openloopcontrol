# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

## Step1:

Initiate the MobileRobot.
## Step2:

Connect your PC with the MobileRobot.

## Step3:
Open Python program.


## Step4:
Program the movements of the robot using python code.


## Step5:
Execute the python program.


## Program:
## Linear movement coding:
```
from robomaster import robot
import time

if __name__ == '__main__':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    '''
    ep_chassis.move(x=2, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=2, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_robot.close()
```
## Circular Movement coding:
```
from robomaster import robot
import time
from robomaster import camera

if __name__ == '__main__':

    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    '''
    x = speed in x direction( meter/second) [-3.5,3.5]
    y = speed in y direction( meter/second) [-3.5,3.5]
    z = rotation about z axis ( degree/second)[-600,600]
    '''
    ep_camera = ep_robot.camera

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)    
    
    ep_chassis.drive_speed(x=0.2,y=0,z=20)
    time.sleep(20)
    ep_chassis.drive_speed(x=0,y=0,z=0)
    
    ep_camera.stop_video_stream()
    print("Stopped video streaming...")
    
    ep_robot.close()
```
## MobileRobot Movement Image:

![robo](./img/robomaster.png)
![robo1](./img/mobo.jpg)
![robo2](./img/mobo2.jpg)






## MobileRobot Movement Video:
Embed video here: 🎬🎬🎬https://www.youtube.com/watch?v=X5581Md0V3I


https://www.youtube.com/watch?v=M9oHs1Cbacw


## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.



```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
