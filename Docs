![LegoWorks](https://user-images.githubusercontent.com/106318228/200198411-2eae259f-2366-4801-989a-78bde47ae537.png)

# LegoWorks-Pico-library
A library for raspberry pi pico designed by us. It's usefull for make robots or using sensors.

This library make's easier to use sensors and motors in order to use on robots.

The clases and methods are:

  ## LED:
  To define a led:
  ~~~~
  led = LED(pin)
  ~~~~
  
  Some methods for LEDs
  ~~~~
  led.on() # To turn it on
  led.off() # To turn it off
  ~~~~
  
  # Sensors:
  
  ## Ultrasonic sensor:
  
  To define the ultrasonic sensor:
  ~~~~
  dist_sensor = DistanceSensor(echo_pin, trigger_pin)
  ~~~~
  
  The method to get the distance in cm:
  ~~~~
  dist_sensor.get_distance_cm()
  ~~~~
  
  ## Integrate temperature sensor:
  
  The Pico comes with an integrated temperature sensor on the RP2040 chip.
  To define the temperature sensor:
  ~~~~
  temp_sensor = TemperatureSensor()
  ~~~~
  
  The method to get the temperature on Cº:
  ~~~~
  temp_sensor.get_temperature()
  ~~~~
  
  ## Buttons:
  
  To define a simple button:
  ~~~~
  button = Button(button_pin)
  ~~~~
  
  Some methods for buttons:
  ~~~~
  button.get_value() # Returns the state of the button. 1 pressed, 0 free.
  ~~~~
  
  ## Gyro sensor:
  
  ### Theory
  A gyro sensor it's for measure angle velocity and angle acceleration, but this library use them as a position angle.
  When you define the object, the program would start a workflow to start the counter. 

  ### In programming:
  
  To define the sensor on an specific axis:
  ~~~~
  gyro = GyroSensor(sda_pin, scl_pin, I2C_channel, axis='z')
  ~~~~
  
  Now, the methods are one for each 3 axis. To change axis you should change the Z to X or Y.
  ~~~~
  gyro.reset_z() # Reset angle origin
  gyro._get_z_angle() # Returns the position on that axis
  ~~~~
  
  # Motors:
  
  ## Single motors:
  
  Note that there are two types of servo motors; continious rotation servo motors and position servo motors, there's only one method for the position servo motors.
  
  To define a servo motor:
  ~~~~
  motor = Motor(motor_pin)
  ~~~~
  
  Some methods for single motors: 
  ~~~~
  motor.start(power) # To start move
  motor.stop() # to stop movement
  motor.moving_for_seconds(power, seconds) # To start moving for some seconds
  ~~~~
  
  ## Angle motor:
  
  This motor it's a servo motor that works only with angle positions. To define it:
  
 ~~~~
 servo = AngleMotor(pin)
 ~~~~
 
 The method to move to a position:
 ~~~~
 servo.move_to_position(angle)
 ~~~~
 Servos normally have an operational range, it's different from one model to another so to normalize the use
 we're gonna use the 90º as the origin because some of servos had only range 0-270º or 0-180º.
       
       
  ## Motor pairs:
  
  To define a motor pair for moving:
  ~~~~
  motor_pair = MotorPair(right_pin, left_pin)
  ~~~~
  
  Some methods for motor pairs:
  ~~~~
  motor_pair.start(right_power, left_power) # To start move
  motor_pair.stop() # To stop movement
  motor_pair.moving_for_seconds(right_power, left_power, seconds) # To start move for some seconds
  ~~~~
  
  ## Chronometer:
  
  The chronometer it's used to count time passed. It can be reseted to 0 or we can see the actual value of it.
  To set the timer:
  ~~~~
  timer = Timer()
  ~~~~
  
  Some methods fot it:
  ~~~~
  timer.reset() # It resets the timer to 0
  timer.get_time() # It returns the time passed after the last reset
  ~~~~
                                                          
                                                            
 # SS1803 library. OLED display.
  
 This is a library for using the oled displays. It can show information or we can make draws.
  
  To define the OLED display:
  ~~~~
  from machine import Pin, I2C
  import ssd1306
  
  i2c = I2C(1, sda=Pin(17), scl=Pin(16))
  display = ssd1306.SSD1306_I2C(128, 64, i2c)
  ~~~~
  
  Now, we print a Hello-world example:
  ~~~~
  display.text('Hello, World!', 0, 0, 1)
  display.show()
  ~~~~
  
  Some basic functions:
  ~~~~
  display.poweroff()     # power off the display, pixels persist in memory
  display.poweron()      # power on the display, pixels redrawn
  display.contrast(0)    # dim
  display.contrast(255)  # bright
  display.invert(1)      # display inverted
  display.invert(0)      # display normal
  display.rotate(True)   # rotate 180 degrees
  display.rotate(False)  # rotate 0 degrees
  display.show()         # write the contents of the FrameBuffer to display memory
  ~~~~
   
  More advance methods:
  ~~~~
  display.fill(0)                         # fill entire screen with colour=0
  display.pixel(0, 10)                    # get pixel at x=0, y=10
  display.pixel(0, 10, 1)                 # set pixel at x=0, y=10 to colour=1
  display.hline(0, 8, 4, 1)               # draw horizontal line x=0, y=8, width=4, colour=1
  display.vline(0, 8, 4, 1)               # draw vertical line x=0, y=8, height=4, colour=1
  display.line(0, 0, 127, 63, 1)          # draw a line from 0,0 to 127,63
  display.rect(10, 10, 107, 43, 1)        # draw a rectangle outline 10,10 to 117,53, colour=1
  display.fill_rect(10, 10, 107, 43, 1)   # draw a solid rectangle 10,10 to 117,53, colour=1
  display.text('Hello World', 0, 0, 1)    # draw some text at x=0, y=0, colour=1
  display.scroll(20, 0)                   # scroll 20 pixels to the right

  # draw another FrameBuffer on top of the current one at the given coordinates
  import framebuf
  fbuf = framebuf.FrameBuffer(bytearray(8 * 8 * 1), 8, 8, framebuf.MONO_VLSB)
  fbuf.line(0, 0, 7, 7, 1)
  display.blit(fbuf, 10, 10, 0)           # draw on top at x=10, y=10, key=0
  display.show()
  ~~~~
  
