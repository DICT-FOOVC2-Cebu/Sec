#CODES

import RPi.GPIO as io
import time 
import datetime 

io.setmode(io.BCM)

sensor_pin =21

io.setup(sensor_pin, io.IN, pull_up_down = io.PUD_UP)
with open ("Output.txt","w") as text_file:
  
   while True:
    if io.input(sensor_pin):
      print("INTRUDER ALERT")
      print "Current date and time: ", time.ctime()
      text_file.write("Intruder alert! Time: %s \n" %(time.ctime()))
      time.sleep(0.5)
    else:
      print("DOOR CLOSED")
      print " Current date and time: %s ",time.ctime()
      
      
      
      
     
