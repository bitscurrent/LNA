# Low Noise Amplifier
  *[Abstract](#abstract)
  *[Reference Circuit Details](#reference-circuit-details)
  *[Reference Circuit Diagram](#reference-circuit-diagram)
  *[Reference Circuit Waveform](#reference-circuit-waveform)
  
  
## Abstract

The proposed Low Noise Amplifier (LNA) with active inductor instead of passive inductor which can save the size of the chip at a great extent. The LNA is designed in 28nm technology for 2.6 GHz frequency range. The LNA presented here offers a good noise performance. The proposed LNA is simulated in synopsis design tool in 28nm technology.
  
## Reference Circuit Details

The current reuse technique is used to design LNA with an aim to reduce the chip area for that an active inductor is used in the gate inductance. In LNA the gate inductance is always higher ~7nH which consumes large area, to overcome the issue an active inductor has been placed which consumes relatively lower area. In fig1 C1 and C2 are DC block capacitors, L1 and L2 are source and drain inductors and the inductor Lm is used to increase the impedance between M1 and M2.
Active Inductor- In fig2 M4 and M5 are current mirror transistors they inverse the conductance value of M3 which is in positive transconductance region and M1 is in negative transconductance region. The three transistors M6,M7,and M8 are used for biasing purpose. And the current Ibias is used for biasing.[3]

## Reference Circuit Diagram
![image] 
