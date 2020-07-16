# FuzzPedal - Introduction
Fuzz Guitar Pedal Tutorial and Explanation

Improve the understanding and application of the following skills:
  - Practice :
    - Breadboard Prototyping
    - Through-hole Soldering
    - 3D Modeling and Printing

  - Theory :
    - Basic Electrical Schematics
    - Analog Filters
    - Voltage Divider

# Step 1 - Breadboard Prototyping
# 1.1 : Components
The following materials are necessary for this project :
  - 9V Battery
  - 10k Resistor
  - 100KΩ Potentiometer* 
  - 1uF Capacitor
  - 100nF Capacitor
  - Diode (one of the following) :
    - Silicon Diode (0.7V Voltage Drop) i.e 1N914, 1N4148, 1N400X
    - Schottky Diodes (0.15-0.45V Voltage Drop) i.e 1N581X, 1N582X, 1N5711, BAT41-43, BAT45-49
  - NPN Transistor (one of the following, higher hfe = more fuzz)** : 
      - MPSA14 (hfe min 10k at 1mA Ic and 5V Vce)
      - MPSA13 (hfe min 5k at 1mA Ic and 5V Vce)
      - MPSA18 (hfe min 500 at 1mA Ic and 5V Vce)
  - 2x 1/4" Stereo Jack, preferably panel-mountable
      - i.e https://www.amazon.ca/Audio-prises-femelle-st%C3%A9r%C3%A9o-Panel/dp/B00CO6Q1II/ref=sr_1_5?dchild=1&keywords=1%2F4%22+stereo+jack&qid=1594875001&sr=8-5
  - Latching Stomp Foot Switch Button DPDT 4-6 pins
      - i.e https://www.amazon.ca/HOUTBY-6Pins-Latching-Switch-Guitar/dp/B07FMPRMSK
        
Notes :
    * Preferably a 100Ka potentiometer because a logarithmic (Log/Audio) scaling of the volume control will be perceived as linear by our ear
    ** Any NPN transistor with similar high gain will work
    
# 1.2 : Schematics
Before explaining the components choices and the theory, here's the project schematics :

