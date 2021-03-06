# Fuzz Pedal - Introduction
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
  - 1uF Capacitor (film capacitor if possible)
  - 100nF Capacitor (must be polarized)
  - Diode (one of the following - See theory for choice) :
    - Silicon Diode (0.7V Voltage Drop) i.e 1N914, 1N4148, 1N400X
    - Schottky Diodes (0.15-0.45V Voltage Drop) i.e 1N581X, 1N582X, 1N5711, BAT41-43, BAT45-49
  - NPN Transistor (one of the following - See theory for choice)** : 
      - MPSA14 (hfe min 10k at 1mA Ic and 5V Vce)
      - MPSA13 (hfe min 5k at 1mA Ic and 5V Vce)
      - MPSA18 (hfe min 500 at 1mA Ic and 5V Vce)
  - 2x 1/4" Stereo Jack, preferably panel-mountable
      - i.e https://www.amazon.ca/Audio-prises-femelle-st%C3%A9r%C3%A9o-Panel/dp/B00CO6Q1II/ref=sr_1_5?dchild=1&keywords=1%2F4%22+stereo+jack&qid=1594875001&sr=8-5
  - Latching Stomp Foot Switch Button DPDT 4-6 Pins
      - i.e https://www.amazon.ca/HOUTBY-6Pins-Latching-Switch-Guitar/dp/B07FMPRMSK
        
Notes :
    * Preferably a 100Ka potentiometer because a logarithmic (Log/Audio) scaling of the volume control will be perceived as linear by our ear
    ** Any NPN transistor with similar high gain will work
    
# 1.2 : Schematics
Before explaining the components choices and the theory, here's the project schematics :

# 1.3 : Theory
The pedal effect circuit can be broken down into two parts.
The Power supply and transistor makes the fuzz effect, hard clipping, filter and amplification of the signal.
The diode in this circuit allows the base voltage to be lower than the collector voltage by the Voltage Drop of the chosen diode.
For the negative peak input signal, the current will pass through the diode towards the base, lowering the collector bias accordingly. It also depends on how much current the resistor allows.
For positive signal creating a difference between the collector voltage and the input voltage lower than the diode voltage drop, the diode will not allow current through. Therefore, the signal will reverse leak through the diode and will be amplified. The amplifier has a maximum output amplification, which clips part of the positive input swing.
The resulting output signal is assymetrically clipped and amplified, creating a unique fuzz sound depending on the input amplitude and the choice of diode and transistor.
The single stage amplifier in this circuit makes the collector current equal to the base current multiplied by the by the transistor current gain. 
## Choosing your diode and transistor
  - A lower voltage drop diode creates more compression from more clipping, but less amplification.
  - A higher transistor current gain (hfe or β) creates more saturation and fuzz.

##
The capacitor C1 is responsible for the high-pass filter. It will block low frequency (bass) signals. THe formula for the critical frequency is fc=1/(2*π*R*C)
For the positive swing, the input impedance is high and the bass frequencies will be cut according to the transistor current gain value. A higher C1 value will also cut less frequencies. The low impedance of the negative swing is dependant on the diode and has a higher frequency pass filter.

Another high-pass filter using C2 blocks low frequencies or DC signals from exiting the pedal. We can calculate this one using the same formula. R equals the potentiometer value (Rpot) and C2 is the capacitor. For example, at maximum Rpot value of 100kΩ and 100nF capacitor value, the frequency cut will be at 16Hz.

Volume control is done with a simple controllable voltage divider with the potentiometer. Vo = Vin * Rground/(Rpot + Rground).

# 1.4 Testing using the breadboard
We start by making the Fuzz effect circuit, then connect the input and output sockets along with the 9V battery. We may then test this circuit with a guitar and amplifier, or an oscilloscope. For the oscilloscope, use a wave signal at the input and the output should show a slpoe increase along with positive clipping. The last step is to add the stomp button, which simply switch the input signal from passing throught the effect circuit to bypassing it. The linked button switch has three channels, but bypassing the third channel with a wire from the input to the output reduces the number of channels to two.
