# iFLO Reflash #  
  
***Do At Your Own Risk ***  
  
I got tired of the iFLO miscounting my dispenses and leaving me with bottles still containing cleaner that I could not use because they have to be registered and are tracked. I also wanted in integrated into Home Assistant and off the cloud. The iFLO uses a ESP32-S2 SOLO. I mapped out most of the pins. The side interface board has some jacks on the side from what i understand are used with the pro model. there are two H-brides to drive motors. They seem to be Mixic MX08H - 32788Hs, the writing is hard to read  because of the coating. U1 is used to drive the motor that dispenses the cleaner while the U3 output goes to the 5.5mm plug on the side interface board.

Here is everything that I traced out.  
![Pinout.png](https://github.com/demitryk1/SmartHome/blob/main/iFLO/Pinout.png?raw=true) 


### How this differs from the original firmware ###
- No more cloud
- You can reuse the bottles with your own cleaner
- Graphical Web Interface
- You can set the dispense amount; 3, 6, 9, or 12 floz. this will automatically update the dispenses left.
- You can set the Dispense schedule; every 7, 14, 30 days, on the 1st of the moth, or the 1st and the 15th of the month
- The front button operation: hold 1 - 5 seconds it will dispense, hold for 10 seconds and it will reset the dispenses left
- LED Operation:
     -- Cloud LED = Solid when one and will blink when running a script (dispense or reset dispense count)
     -- WIFI LED = Solid when connected, Blinking when not connected
     -- Battery LED = On when 20% or less
     -- Bottle LED = On if dispense left count is  or bottle is removed 

Here is an image of the dashboard for clarification:

![Dashboard.png](https://github.com/demitryk1/SmartHome/blob/main/iFLO/Dashboard.png?raw=true) 


### What You Need ###  
- philps head screwdriver   
- USB_Serial Converter, I used a SH-U09BL_CP2102N
- Something conductive to short the boot pin to ground
- a way to interface to the pins to flash the board, solder some wire or use a helping hands setup.
- the bin or the yaml file

### Instructions - ESP32Home Builder ###
- Remove the hose from the unit
- Remove the two screws from the bottom
- Disconnect the 4 plugs from the board, they are color coded so do worry about documenting what went where
- Remove the board housing by removing the two screws holding the board housing in place, press the front button in to clear the casing.
- Remove the board from the button housing
- Attach your USB-serial converter to the pins shown on the pinout image above (VCC, GND, TXD, RXD).
    Note: you may have to reverse the TXD and RXD pins depending on the converter.
- Short the two pads labeled bootloader


I've done 2 of these now, I soldered one and i used some helping hands on the other. i found the helping hands to be cleaner.

Helping Hands:
![Helping_Hands.png](https://github.com/demitryk1/SmartHome/blob/main/iFLO/Helping_Hands.png?raw=true) 





