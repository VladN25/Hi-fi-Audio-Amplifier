
<h1>Hi-fi Audio Amplifier</h1>

<h2>Description</h2>
I have made the full schematic and PCB design of a Hi-fi class D Audio Amplifier. Not only have I designed it, but i also ordered the PCB, soldered all the components in place, tested, troubleshooted and verified the whole circuit. I used the EasyEDA tool in order to bring this project to life and create the manufacture folders for the final order. All of the components that were used are THD format, including the ICs and voltage regulators.
<br />

<h2>The Technology of the Circuit</h2>
The basic idea was quite straight forward. I planned to use a 555 timer IC to generate a high frequency ramp waveform (~300kHz) that would enter the inverting input of a LM393 comparator, along with a modulating signal coming from the jack port of a laptop. The comparator would output a 300kHz digital signal that would be the carrier. The carrier along with the modulated signal would enter a CMOS circuit in order to amplify the digital signal in amplitude, but also to enter a Low Pass filter that could reconstruct the original modulated signal. This procedure would have been efficient because a normal speaker can't function without a considerable amount of current, which the laptop audio port cannot give. However, along the way I encountered a few non-ideal aspects and flaws. 
<br />

<h2>Encountered Problems</h2>
However, along the way I encountered a few non-ideal aspects and flaws. First, the two mosfets from the CMOS configuration are obviously mismatched. That would be because the mobility of the p-type MOS is smaller, hence the current flowing through it would be slower than the one from the nMOS. Because of the high frequency of the carrier there would be much distorsion on the digital signal due to parasitic inductances in the copper traces. To reduce these distortions, I thought about using decoupling capacitors on all the power pins from every IC. However, if the capacitors were not very close to these pins, it would change nothing. These were some of the most problematic flaws and in the next paragraph I am going to give the solutions that I have found to compensate for them. 
<br />

<h2>The solutions I found</h2>
For the first problem, I changed the pMOS to an identical nMOS, and in order to drive both of their gates I used a IR2113 MOS driver. The driver also needed to amplify the output digital signal, so I used a double power supply, 5V at the input and 12V at the output (coming from 2 voltage regulators). Because one mosfet needed to be on while the other one was off I needed to feed the driver 2 digtal signal: the original carrier and its inverse. For the inverse of the carrier I used a 74HC14 inverter IC. 
For the second problem, I made sure as far as I could to limit the copper traces length by compressing the circuit on the PCB, but I also added decoupling capacitors close enough to the power pins. I put a 1mF capacitor on on the output jumper in series to center the sine wave. The cut-off frequency that I calculated for the LPF was set to 40kHZ and I used a 1uF equivalent capacitance and a 16uH equivalent inductance. 
<br />


<h2>The Schematic and the PCB</h2>
<p align="center">
<img src="https://imgur.com/axtmQzw.png="80% width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://imgur.com/dlgSFLe.png="80% width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://imgur.com/yMFXHKI.png="80% width="80%" alt="Disk Sanitization Steps"/>
<br /> All of the manufacturing files are pinned to this repository.    <br />  
<br />

<h2>The physical project</h2>
<p align="center">
<img src="https://imgur.com/GS3VXIU.png="80% width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/gjVDvwh.png="80% width="80%" alt="Disk Sanitization Steps"/>
<br />


<p align="center">
  Watch video:  (https://imgur.com/JQsv8sC)

 <br/>

