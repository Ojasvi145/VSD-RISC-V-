# Week 4 Task – CMOS Circuit Design (sky130-style)

## Objective
This task deepens our understanding of how transistor-level circuit properties (devicephysics, sizing, variation) drive the timing behavior that STA analyzes. By working throughCMOS design and SPICE simulations (as in the sky130 workshop), you will see the “real”side of what STA approximates. This strengthens your intuition about slack, delay, noisemargins, and variation impacts.

### Context
This comprehensive summary explores two foundational pillars of modern VLSI design: power-aware clock tree synthesis (CTS) and MOSFET device physics. The CTS section outlines a hierarchical buffering strategy that employs identical buffers at each level of the clock tree. This uniformity ensures consistent capacitive loading across all branches, enabling predictable delay propagation and minimizing timing skew. Delay characterization tables for various buffer types—such as CBUF-X, CBUF-Z, CBUF-1, and CBUF-2—illustrate how delay varies with output load and input slew, allowing designers to make informed buffer selections that balance power and performance. This methodology supports the construction of low-power, high-speed clock distribution networks by optimizing fanout and load symmetry.

Shifting to MOSFET physics, the discussion begins with the structural anatomy of an NMOS transistor, emphasizing the roles of the gate, source, drain, and substrate in channel formation. The concept of threshold voltage is introduced as the critical gate-to-source voltage required to initiate strong inversion, thereby forming a conductive channel between source and drain. A central focus is the body effect, which describes how a positive substrate bias increases the threshold voltage due to an expansion of the depletion region near the source-substrate junction. This phenomenon necessitates additional gate voltage to achieve inversion, impacting device switching behavior.

Supporting this analysis are foundational semiconductor principles, including the definition of oxide capacitance and the relationship between Fermi potential and doping concentration. These parameters influence the electrostatic behavior of the transistor and are essential for accurate modeling. The narrative then advances to the resistive operation region, where the channel exhibits a non-uniform charge distribution caused by the voltage gradient along its length. This spatial variation in charge leads to a position-dependent current flow, governed by the mobility of charge carriers and the local electric field. The resulting drain current reflects the dynamic interplay between gate voltage, threshold voltage, and channel potential.

Finally, the discussion distinguishes between two fundamental types of current in semiconductor devices: drift current, which arises from electric fields, and diffusion current, which is driven by gradients in carrier concentration. Together, these concepts provide a rigorous framework for understanding transistor behavior under bias and inform the design of energy-efficient digital systems.

![Alt text](IMAGES/1.png)
![Alt text](IMAGES/2.png)
![Alt text](IMAGES/3.png)
![Alt text](IMAGES/4.png)
![Alt text](IMAGES/5.png)
![Alt text](IMAGES/6.png)
![Alt text](IMAGES/7.png)
![Alt text](IMAGES/8.png)
![Alt text](IMAGES/9.png)
![Alt text](IMAGES/10.png)
![Alt text](IMAGES/11.png)
![Alt text](IMAGES/12.png)
![Alt text](IMAGES/13.png)
![Alt text](IMAGES/14.png)
![Alt text](IMAGES/15.png)
![Alt text](IMAGES/16.png)
![Alt text](IMAGES/17.png)
![Alt text](IMAGES/18.png)
