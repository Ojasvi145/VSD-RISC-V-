# Week 4 Task – CMOS Circuit Design (sky130-style)

## Objective
This task deepens our understanding of how transistor-level circuit properties (devicephysics, sizing, variation) drive the timing behavior that STA analyzes. By working throughCMOS design and SPICE simulations (as in the sky130 workshop), you will see the “real”side of what STA approximates. This strengthens your intuition about slack, delay, noisemargins, and variation impacts.

### Context
The collection of diagrams and equations presents a comprehensive exploration of MOSFET device physics and power-aware clock tree synthesis (CTS), both foundational to modern VLSI design. The CTS section introduces a structured buffering strategy using identical buffers across two hierarchical levels, ensuring uniform capacitive loading and predictable delay propagation. Delay tables for various buffer types (e.g., CBUF-X, CBUF-Z, CBUF-1, CBUF-2) quantify timing behavior under varying output loads and input slews, enabling comparative analysis for optimal buffer selection. This approach supports low-power, high-performance clock distribution by minimizing skew and balancing fanout. Transitioning to MOSFET physics, the material begins with the structural anatomy of an NMOS transistor, detailing the role of the gate, source, drain, and substrate in channel formation. The concept of threshold voltage (Vₜ) is introduced as the gate-to-source voltage required to induce strong inversion, thereby enabling conduction. A key focus is the body effect, where a positive substrate bias (V_sb) increases Vₜ due to enhanced depletion near the source-substrate junction. This is mathematically modeled using the expression 
| **Parameter**         | **Formula**                                                                                                                             |
| :-------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| **Flat-Band Voltage** | $V_{FB} = \phi_{ms} - \dfrac{Q_{ss}}{C_{ox}} \quad (\phi_{ms} = \phi_m - \phi_s)$                                                       |
| **Threshold Voltage** | $V_T = V_{FB} + 2\phi_F + \dfrac{\sqrt{4 \epsilon_s q N_A \phi_F}}{C_{ox}}$                                                             |
| **Body Effect**       | $V_T = V_{T0} + \gamma \left( \sqrt{2\phi_F + V_{SB}} - \sqrt{2\phi_F} \right) \quad (\gamma = \frac{\sqrt{2q\epsilon_s N_A}}{C_{ox}})$ |, where γ is the body effect coefficient and ϕ_f is the Fermi potential. Supporting equations define oxide capacitance \( C_{ox} = \varepsilon_{ox} / t_{ox} \) and relate Fermi potential to doping concentration via \( \phi_f = \phi_r \ln(N_A / n_i) \). The analysis then progresses to the resistive operation region, where the channel exhibits a non-uniform charge distribution due to the voltage gradient along its length. The inversion charge at any point x is given by \( Q(x) = -C_{ox}[(V_{gs} - V_t) - V(x)] \), and the corresponding drift current is derived as \( I_d = \mu_n C_{ox}[(V_{gs} - V_t) - V(x)] \frac{dV(x)}{dx} \), integrating over the channel length to obtain the I-V characteristics. The discussion concludes by distinguishing drift current—driven by electric fields—from diffusion current, which arises from carrier concentration gradients. Together, these insights form a rigorous framework for understanding transistor behavior under bias and for designing energy-efficient clock networks in digital systems.

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
