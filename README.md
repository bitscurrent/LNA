# Low Noise Amplifier

This repository presents the design of Low Noise Amplifier with active inductor using Synopsis Custom Compiler on 28nm CMOS Technology node.

# Table of Contents
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
![schematic dia LNA with inductor](https://user-images.githubusercontent.com/43288153/155196548-7ddb7448-8ef3-4b82-89fb-6f2d146cc52f.jpg)
                                        fig1 Schematic Diagram of LNA   

![WhatsApp Image 2022-02-19 at 4 39 44 PM](https://user-images.githubusercontent.com/43288153/155195794-92e132a2-4809-41b2-876a-e4d1d8261791.jpeg)
                                        fig2. Active Inductor
## S-Parameter Setting
![s-param setting](https://user-images.githubusercontent.com/43288153/156167248-5989189d-73fb-4b0d-b0bd-1f9902993da3.jpg)


## Noise Setting

## Schematic Diagram 

## Waveforms
fig Scattering Parameter (S11).

fig Output Noise.

## Conclusion
Thus, an LNA .... is verified using 28nm Technology node on Synopsis Compiler.

## Acknowledgement

1.  Kunal Ghosh, Co-founder,VSD Corp.Pvt. Ltd.- kunalpghosh@gmail.com

2. Chinmay Panda, IIT Hyderabad

3. Sameer Durgoji, NIT Karnataka

## References

1. Rajan Kumar, DivyeshSachan, Sonu Singh Yadav, Ankit Kumar Sihara and Prasanna Kumar Misra, 2017, „Design of Active Inductor at 2.4 GHz frequency using 180 nm CMOS Technology‟,4th IEEE Uttar Pradesh Section International Conference on Electrical, Computer and ElectronicsK. Elissa, “Title of paper if known,” unpublished.
2. M.Malleshwari and S.Manjula , 2017, Design of CMOS High Linear Low Noise Amplifier for Small Satellite Ground Station‟ , National Conference on Small Satellite Technology and Applications J. Clerk Maxwell, A Treatise on Electricity and Magnetism, 3rd ed., vol. 2. Oxford: Clarendon, 1892, pp.68–73.
3. M. I. Malek, S. Saini, “Designing a fully integrated low noise tunableQ Active Inductor for RF applications,” International Journal of Engineering Research & Technology, Vol. 1 Issue 4, June – 2012.
4. Anantharaju Sandhya rani , Ramya.G, Tallapalli Padma,Suganthy.M “Design of CMOS current reuse low noise amplifier using modified active inductor,” International Journal of Pure and Applied Mathematics Volume 119 No. 15 2018, 723-732.
