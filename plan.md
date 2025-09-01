(All times are in GMT+6)
# 9:14 PM August 31
Alright, this is my plan for the project:
Project sections:
- Hardware: this is the thing that you can touch
- Software: the software for the display
- Protocol designing: how the pc talks with the display
- (2nd priority) Libraries: a Python library to use the display, maybe just a script that you can import\
                            TO BE CLEAR: this is the software running on the connected PC, not on the display itself
- (3rd priority) Either a graphing app or an integration with desmos
# 9:18
Ok, now for specific plans:
( parts list moved to parts.md )

finally im done with parts list

- 1x RPi Pico, price: free through inventory
- 1x stepper driver price: free through inventory
- 1x SSD1306 price: free through inventory
- 1x Slip Ring price: us$8.99 through grant
- 1x 3D print or bare pcb price: either shipping (paid through grant) or 0 price if bare pcb

## even more hardware
## everything thats not the parts list

there will be two sections.

1) base: stationary.
houses the rpi, oled, slip ring, stepper motor, and the usb cable
there may or may not be a case around it, these will all be mounted on a PCB
2) spinny thing!
this is essentially only the LCD attached to the motor. then the wires will go through the slipring.
3) protection case maybe?
some acrylic thing around it if I can find a cheap one

## finally, software
# software
the algorithm is simple:
thread/core 1 loop: 
- thetasync (vsync but 3d, read rest of algorithm is confused) starts at false
- check if a new 3D frame is being sent through whatever protocol i have
    - if so, read it
    - after read finished, set the current 3D frame in core 2 if thetasync is false
    - if thetasync is on, set change pending in core2 to true and the requested frame as current frame
- if its a command being sent
    - do whatever it says like enable thetasync
- if a speed ( controls theta resolution + refreshrate ) change command
    - change speed variable in core 2
- if a rotation command:
    - (this is a optimized way to rotate the screen theta-wise without rendering a new 3D frame, this shifts the pixel grid as well making it seem smooth)
    - send a rotation command to core 2 with theta offset
- if a start/stop command:
    - do that
- print whatever needed in the oled (again not spinning)
thread/core 2 loop:
- speed is starts at some default value
- current 3D frame starts at black/empty
- started starts at false
- rotation offset starts at 0
- current rotation also at 0
- thetasync is same as core 1
- change pending is false
- pending frame is empty/black
- if started (changed by core1):
    - check the current 2d frame to render using current rotation
    - display it
    - increment current rotation by speed
    - rotate stepper by speed
    - do the modulo thing for current rotation (0 to 360 or 0 to 2pi)
- if rotation offset is not 0:
    - rotate motor by that
    - set offset var to 0
- if change pending (after rendering):
    - if current rotation is close to 0 (by 1 degree or something either direction), 
        - set current frame = pending frame
        - set change pending to false
    - otherwise do nothing

this will spin the lcd and display the things required at the correct time. the algorithm is designed to not get bonked when it loses a step (it will just rotate slightly) and it also is designed to only use relative rotation. 
look all rotation statements are "rotate by" and never "rotate to".
nema 17 motor can reach 5k rpm ideally, but even not ideally its 600 to 3k with torque decreasing with rpm.
BUT WE DONT NEED TORQUE! we just need speed! this is not a robot vehicle.


# protocol

time now: 11:05 pm 
i will work later 

ok its 6 10 pm next day (sept 1) rn
lemme research usb stuff
ok so the default usb cdc uart thing is not baudrate limited so i will use that
here is my idea:
1) you start a command with ascii charecter. a=display frame,b=speed,s=start,!=stop,r=rotate,0=thetasync on, 1=thetasync off
2) for a,you can send binary data where is byte is one R,G or B value. then, use : after R,G,B chars to indicate the end of pixel and / for end of frame
example: (assume (0xAB) is the charecter in ascii corresponding to 0xAB)
(0xFF)(0x00)(0x00):(0x00)(0x00)(0xFF)/ would indicate a frame with a red pixel with color #FF0000 and a blue pixel with color #0000FF then end of frame.
3) for command b, the syntax is b then integer/float value in decimal then / to end. same for rotate with degree value
4) s , ! , 0 , 1 need no params
5) OR new commands can be implemented with &(command here)/(params)/ if needed

ok now I am seperating parts list into a new file bc i may edit it
done
now time to design the hardware in wokwi, its 6 52 rn
ok this is my link im desinging it [Wokwi project](https://wokwi.com/projects/new/micropython-pi-pico)
one thing I realized: i may not need the OLED so im removing it
yeah turns out I need a 12 volt power supply for the motor
so i will have to use a 5v dc encoder motor.