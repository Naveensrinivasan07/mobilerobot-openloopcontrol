###MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:

Use from robomaster import robot.

<br/>

Step2:

Choose the x,y,z - axis movement distance(meters).

<br/>

Step3:

Give ep_chassis.move to move straight.

<br/>

Step4:

Give time.sleep() for a break.

<br/>

Step5:

Give ep_chassis.drive_speed to have a circular movement.

<br/>

## Program
```python
#DEVELOPED BY :NAVEEN S
#REG NO. : 212222240070

from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
          
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    ''' 
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5] 
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second)  [0.5,2]

    '''
    ep_chassis.move(x=4, y=0, z=0, xy_speed=1).wait_for_completed()
 
    ep_chassis.move(x=0, y=0, z=55, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=124,b=112,effect="on")  
    ep_chassis.move(x=3, y=0, z=0, xy_speed=1).wait_for_completed() 

    '''
    x = speed in x direction( meter/second) [-3.5,3.5]
    y = speed in y direction( meter/second) [-3.5,3.5]
    z = rotation about z axis ( degree/second)[-300,300]
    '''
    ep_led.set_led(comp="all",r=255,g=220,b=70,effect="on")  
    ep_chassis.drive_speed(x=0.4,y=0,z=-20)
    time.sleep(12)
    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on") 
    ep_chassis.move(x=2.95, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=128,effect="on") 
    
    
    ep_chassis.move(x=0.1, y=0, z=60, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=170,g=0,b=0,effect="on") 
    ep_chassis.move(x=0.8, y=0, z=0, xy_speed=1).wait_for_completed()

    ep_chassis.drive_speed(x=0.2,y=0,z=-20.5)
    time.sleep(4)
    
    ep_chassis.move(x=2.8, y=0, z=0, xy_speed=1).wait_for_completed()

    
    
    

    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

Insert image here
(![Screenshot 2023-06-05 111755](https://github.com/Naveensrinivasan07/mobilerobot-openloopcontrol/assets/119475891/760caa70-a746-408d-8696-ed3168bdd9d3)
(![Screenshot 2023-06-05 111814](https://github.com/Naveensrinivasan07/mobilerobot-openloopcontrol/assets/119475891/481b9feb-e92c-4ddb-8cd4-c912a3f7bc50)


## MobileRobot Movement Video:
Upload your video in Youtube and paste your video-id here
[(https://youtube.com/shorts/Xbq9WofmPYA?feature=share)]

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

