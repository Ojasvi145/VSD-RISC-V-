# Week 4 Task – CMOS Circuit Design (sky130-style)

## Objective
This task deepens our understanding of how transistor-level circuit properties (devicephysics, sizing, variation) drive the timing behavior that STA analyzes. By working throughCMOS design and SPICE simulations (as in the sky130 workshop), you will see the “real”side of what STA approximates. This strengthens your intuition about slack, delay, noisemargins, and variation impacts.

### Context
This comprehensive summary explores two foundational pillars of modern VLSI design: power-aware clock tree synthesis (CTS) and MOSFET device physics. The CTS section outlines a hierarchical buffering strategy that employs identical buffers at each level of the clock tree. This uniformity ensures consistent capacitive loading across all branches, enabling predictable delay propagation and minimizing timing skew. Delay characterization tables for various buffer types—such as CBUF-X, CBUF-Z, CBUF-1, and CBUF-2—illustrate how delay varies with output load and input slew, allowing designers to make informed buffer selections that balance power and performance. This methodology supports the construction of low-power, high-speed clock distribution networks by optimizing fanout and load symmetry.

Shifting to MOSFET physics, the discussion begins with the structural anatomy of an NMOS transistor, emphasizing the roles of the gate, source, drain, and substrate in channel formation. The concept of threshold voltage is introduced as the critical gate-to-source voltage required to initiate strong inversion, thereby forming a conductive channel between source and drain. A central focus is the body effect, which describes how a positive substrate bias increases the threshold voltage due to an expansion of the depletion region near the source-substrate junction. This phenomenon necessitates additional gate voltage to achieve inversion, impacting device switching behavior.

Supporting this analysis are foundational semiconductor principles, including the definition of oxide capacitance and the relationship between Fermi potential and doping concentration. These parameters influence the electrostatic behavior of the transistor and are essential for accurate modeling. The narrative then advances to the resistive operation region, where the channel exhibits a non-uniform charge distribution caused by the voltage gradient along its length. This spatial variation in charge leads to a position-dependent current flow, governed by the mobility of charge carriers and the local electric field. The resulting drain current reflects the dynamic interplay between gate voltage, threshold voltage, and channel potential.

Finally, the discussion distinguishes between two fundamental types of current in semiconductor devices: drift current, which arises from electric fields, and diffusion current, which is driven by gradients in carrier concentration. Together, these concepts provide a rigorous framework for understanding transistor behavior under bias and inform the design of energy-efficient digital systems.

1.This plot shows Id vs Vgs curve for nmos having width=0.375um length=0.25um
![Alt text](IMAGES/1.png)
2.This plot shows Id vs Vgs curve for nmos having width=1.8um length=1.2um
![Alt text](IMAGES/2.png)
Above plots tells that as width increases drain current increases.
![Alt text](IMAGES/3.png)

3.This plot shows Id vs Vds curve for nmos having width=0.375um length=0.25um
![Alt text](IMAGES/4.png)
4.This plot shows Id vs Vds curve for nmos having width=1.8um length=1.2um
![Alt text](IMAGES/5.png)

5.CMOS inveter where switching threshold is around=0.881148 i.e Vdd/2
![Alt text](IMAGES/6.png)
![Alt text](IMAGES/7.png)

6.CMOS delay calculation
![Alt text](IMAGES/8.png)
Rise time=2.48397-2.15385=0.33012nsec
![Alt text](IMAGES/9.png)
Fall time=4.33504-4.05128=0.28376nsec
![Alt text](IMAGES/10.png)

7.CMOS inverter having Voh=1.73182V Vil=0.762295V Vol=0.1V Vih=0.979508V
Noise margin high=0.752312V : Noise margin low=0.662295V
![Alt text](IMAGES/11.png)

8. Gain(dc6)=(1.74545-0.113636)/(0.974359-0.75641)=7.487136899
![Alt text](IMAGES/12.png)
   Gain(dc5)=(1.51918-0.083636)/(0.876068-0.709402)=8.613298453
![Alt text](IMAGES/13.png)
   Gain(dc4)=(1.33636-0.0681818)/(0.769231-0.645299)=9.981819982
![Alt text](IMAGES/14.png)
   Gain(dc3)=(1.15909-0.05)/(0.67094-0.559829)
![Alt text](IMAGES/15.png)
   Gain(dc2)=(0.968182-0.05)/(0.58547-0.487179)
![Alt text](IMAGES/16.png)
   Gain(dc1)=(0.754545-0.05)/(0.5-0.431624)
![Alt text](IMAGES/17.png)

So above observation tells gain increases as Vin and Vout decreses.
If pfet width increased compared to nfet that means in vtc 1.8 stays staraight for longer time than gnd(device variation),strong pfet weak nfet and vm=1.8/2 should have been ideal but it is right shifted now.(Vm is 0.988)
So therefore we say cmos is very robust
![Alt text](IMAGES/18.png)
