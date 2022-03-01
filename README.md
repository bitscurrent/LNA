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
![noise setting](https://user-images.githubusercontent.com/43288153/156167514-75babda2-811b-4f1d-b8b4-648c486e20df.jpg)


## Schematic Diagram 
![amplifier schematic](https://user-images.githubusercontent.com/43288153/156167605-57f4d15c-c9e1-407d-9b5c-a9badef95645.jpg)
fig: circuit diagram of amplifier section

![testbench](https://user-images.githubusercontent.com/43288153/156170021-1f9ed4af-8e80-473a-81da-32712153887e.jpg)
fig: testbench of LNA

## Symbols
![active inductor symbol](https://user-images.githubusercontent.com/43288153/156167699-aacded32-bf77-4753-95a3-d2682213bf7a.jpg)
fig: active inductor symbol

![amplifier symbol](https://user-images.githubusercontent.com/43288153/156167772-93076391-c3d4-4abf-9640-a4122fd2e114.jpg)
fig: symbol of amplifier section 

![LNA symbol](https://user-images.githubusercontent.com/43288153/156167874-ef68436b-89c4-474c-b9f6-01455365876c.jpg)
fig: symbol of LNA

## Netlist
'''
*  Generated for: PrimeSim
*  Design library name: sm_LNA_new
*  Design cell name: sm_Amplifier_1_tb
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Tue Mar  1 12:03:26 2022

.global gnd!
********************************************************************************
* Library          : sm_LNA_new
* Cell             : sm_Amplifier_1
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt sm_amplifier_1 input output vdd vss
xm0 output vdd net2 net2 n105 w=0.1u l=0.03u nf=1 m=1
xm1 net3 input net4 vss n105 w=0.1u l=0.03u nf=1 m=1
l2 net2 net3 l=3.07n
l3 net4 vss l=1.125n
l8 vdd output l=2.5n
c4 output output c=400f
c5 net2 vss c=1p
c7 vdd net3 c=10u
c9 input net4 c=400f
.ends sm_amplifier_1

********************************************************************************
* Library          : sm_LNA_new
* Cell             : sm_LNA_active_inductor
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt sm_lna_active_inductor isource vdd vss out
xm7 net47 net32 out out n105 w=0.1u l=0.03u nf=1 m=1
xm4 net18 net32 out out n105 w=0.1u l=0.03u nf=1 m=1
xm3 net49 net36 net15 net15 n105 w=0.1u l=0.03u nf=1 m=1
xm2 net15 net18 vss vss n105 w=0.1u l=0.03u nf=1 m=1
xm1 net36 isource net60 net60 n105 w=0.1u l=0.03u nf=1 m=1
xm0 net60 net15 vss vss n105 w=0.1u l=0.03u nf=1 m=1
xm11 net47 net49 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm10 isource isource vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm9 net49 isource vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm8 net36 isource vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
c12 net49 vss c=680f
r18 net32 vdd r=1k
r17 vdd net18 r=1k
r16 isource vdd r=4k
.ends sm_lna_active_inductor

********************************************************************************
* Library          : sm_LNA_new
* Cell             : sm_Amplifier_1_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net16 output net1 gnd! sm_amplifier_1
xi11 net19 net5 gnd! net16 sm_lna_active_inductor
c24 output gnd! c=1490f
c2 input net5 c=1n
p2 output gnd! port=2 dc=0 z0=50
p1 input gnd! port=1 dc=0 z0=50
v17 net26 gnd! dc=1
v16 net5 gnd! dc=1.2
v6 net1 gnd! dc=1.2
i15 net19 gnd! dc=120u
r19 net16 net26 r=200








.lin dec '20' '500meg' '10G' format=touchstone dataformat=ri noisecalc=1 iport=2
+ oport=1 mixedmode2port=ss ports=p2 p1 name=lin
.noise v(output,gnd!) p1 1 dec '20' '500meg' '10G' name=noise

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL
.option primesim_noise_format = 2






.end
'''
## Waveforms
![s-param waveform final](https://user-images.githubusercontent.com/43288153/156167943-91e52f52-fdcf-484d-816a-57db41a89294.jpg)
fig scattering parameter (S11)


![output noise](https://user-images.githubusercontent.com/43288153/156168019-4041c71a-1515-48c5-9711-1ab86705afe5.jpg)
fig output noise.

## Conclusion
Thus, the LNA shows a proper maching at 2.5GHz and is verified using 28nm Technology node of Synopsis.

## Acknowledgement

1.  Synopsys Team/Company.
  
2.  Kunal Ghosh, Co-founder,VSD Corp.Pvt. Ltd.- kunalpghosh@gmail.com
3.  Chinmay Panda, IIT Hyderabad
4.  Sumanto Kar, Sr. Project Technical Assistant, IIT Bombay  

5.  Sameer Durgoji, NIT Karnataka

## References

1. Rajan Kumar, DivyeshSachan, Sonu Singh Yadav, Ankit Kumar Sihara and Prasanna Kumar Misra, 2017, „Design of Active Inductor at 2.4 GHz frequency using 180 nm CMOS Technology‟,4th IEEE Uttar Pradesh Section International Conference on Electrical, Computer and ElectronicsK. Elissa, “Title of paper if known,” unpublished.
2. M.Malleshwari and S.Manjula , 2017, Design of CMOS High Linear Low Noise Amplifier for Small Satellite Ground Station‟ , National Conference on Small Satellite Technology and Applications J. Clerk Maxwell, A Treatise on Electricity and Magnetism, 3rd ed., vol. 2. Oxford: Clarendon, 1892, pp.68–73.
3. M. I. Malek, S. Saini, “Designing a fully integrated low noise tunableQ Active Inductor for RF applications,” International Journal of Engineering Research & Technology, Vol. 1 Issue 4, June – 2012.
4. Anantharaju Sandhya rani , Ramya.G, Tallapalli Padma,Suganthy.M “Design of CMOS current reuse low noise amplifier using modified active inductor,” International Journal of Pure and Applied Mathematics Volume 119 No. 15 2018, 723-732.
