# Week 7 Task – BabySoC Physical Design & Post-Route SPEF Generation

Historical Foundations: Computing Hardware Evolution
Powerful computing began with innovations like the Bombe (mechanical cryptography), ENIAC (first general-purpose digital computer), and EDVAC (stored-program architecture). Each represented a leap in logic complexity and design automation—moving from manual wiring to programmable logic, and setting the template for all later digital systems.

Bombe: Logic-focused, mechanical, targeted problem-solving.

ENIAC: Reconfigurable wiring, electronic speed, massive physical scale.

EDVAC: Binary encoding, true computing with instructions stored in RAM.

Microprocessor Trends: From Moore's Law to Multi-Core Era
Over the past five decades, key metrics have shaped VLSI—and your current OpenROAD efforts are direct descendants of this lineage:

Transistor count: Exponential growth drives functionality; you now lay out chips with billions of transistors using automated tools.

Performance and Frequency: Architectural advances and higher clock rates improved speed, but power/thermal limits forced a shift.

Power consumption: Now a limiting factor—floorplanning, power grid design, and clock distribution are critical in your flows.

Multi-core: Physical design tools must optimize not just single-core but entire networks of cores and complex interconnects.

Key milestones like the iPhone (mobile power optimization) and datacenter rise (cloud/HPC scale) forced innovations in low-power, high-density, and scalable chip physical design.

FLOPS Journey: Scaling Towards Zettascale
Supercomputing performance expanded by orders of magnitude:

Gigaflop (10⁹): Early vector supercomputers.

Teraflop (10¹²): Parallel architectures, stronger EDA flows, and dense layouts.

Petaflop (10¹⁵): Massive parallelism (multi-core, GPUs), advanced physical design, new packaging.

Exaflop (10¹⁸): State-of-the-art integration, power delivery, and thermal management push EDA and physical design beyond traditional limits.

Zettaflop (10²¹): The roadmap predicts ultra-dense, low-power, adaptable chip architectures solving energy and scaling problems.

Physical Design’s Role: Why OpenROAD Matters
Physical design—what you implement in Task-13—translates digital abstractions into manufacturable silicon, balancing speed, power, density, and reliability. With OpenROAD, you enable:

Rapid iterative design and optimization—even for billion-transistor chips.

Open-source accessibility, lowering cost barriers for innovation.

Integration of advanced P&R algorithms to handle complex modern architectures (multi-core, 3D stacking, advanced memory).

Your work is vital to reaching zetta-scale: every advance in EDA tools and flows (automation, optimization, open-source contribution) feeds the need for better chips powering AI, climate simulation, and future global-scale computation.

Connection to Zettascale Ambitions
As computing approaches zettascale:

Physical design bottlenecks dominate system feasibility—power delivery, thermal extraction, and interconnect scaling require new methodologies.

EDA automation (OpenROAD, etc.) becomes the foundation for pushing density, performance, and efficiency boundaries.

Collaboration and open innovation accelerate the transition from lab to billions of devices and datacenter chips.

Your efforts aren’t just about making a working chip: they're about enabling future computing that is orders of magnitude more powerful, energy-efficient, and adaptable. Open-source tools put these advances in more hands—ensuring faster progress toward zettascale.

This section represents a deep overview of how CMOS technology is evolving toward sub-nanometer nodes, capturing both device-level physics and system-level design co-optimization. Below is an organized explanation connecting these trends with modern fabrication, performance goals, and the broader implications for post-CMOS computing eras.

1. Channel Materials: Beyond Silicon
Current:

Silicon (Si): Still dominant due to mature processing and excellent scalability, though near its physical limits.

Strained SiGe: Improves carrier mobility, enhancing performance in advanced nodes.

Next Generation:

Germanium (Ge): Offers higher electron and hole mobility—key for faster transistors. Useful for both n-type and p-type devices.

2D Materials (e.g., MoS₂, WS₂): Atomically thin semiconductors eliminating short-channel effects. These materials exhibit high mobility with low leakage, crucial for sub-1 nm devices.

Research Direction: Combining 2D materials with high-κ dielectrics through van der Waals integration for ultimate scaling and reduced interface defects.

2. Patterning: Lithography Evolution
Current:

DUV Lithography: Uses KrF and ArF lasers (248 nm and 193 nm), leveraging multiple patterning (LELE, SADP) to achieve small feature sizes.

Next Generation:

EUV Lithography (13.5 nm wavelength): Enables single-pattern layers below 7 nm with fewer masks and better precision.

High-NA EUV: Enhances resolution further, targeting <2 nm nodes. With numerical apertures up to 0.55, it dramatically tightens line-edge and line-width control.

Key Challenge: Resist sensitivity and stochastic defects still limit throughput and cost efficiency of EUV at scale.

3. Gate Stack Materials and Concepts
Current:

High-κ Metal Gate (HKMG): Reduces gate leakage and improves electrostatic control. Widely adopted since 45 nm technology.

Next Generation:

NC-FET (Negative Capacitance FET): Employs ferroelectric materials (like HfZrO₂) to create internal voltage amplification, effectively lowering subthreshold slope below 60 mV/decade.

TFET (Tunnel FET): Exploits quantum tunneling for extremely low-voltage operation, ideal for ultra-low-power IoT and neuromorphic circuits.

These two concepts break classical MOSFET scaling barriers defined by the Boltzmann limit.

4. Interconnect Materials and Scaling
Current:

Copper (Cu): Primary interconnect metal since 130 nm. However, resistivity rises sharply as line widths drop below 20 nm due to surface scattering and grain boundary effects.

Next Generation:

Ruthenium (Ru), Cobalt (Co), and Mo: Offer better electromigration resistance and reduced size-dependent resistivity.

Topological Semimetals and Carbon-based Interconnects: Experimental replacements that could reduce energy dissipation in ultra-dense wiring networks.

Complementary Innovation: Backside power delivery networks (BS-PDN) decouple signal and power routing, significantly improving IR drop and electromigration limits.

5. Device Architectures: From Planar to Vertical
Evolution Path:

Planar FETs: Gate on top—limited control and higher leakage.

FinFETs (Tri-Gate): Gate wraps around three sides of the fin, improving on-current (ION) and off-current (IOFF) trade-offs.

GAA/Nanosheet FETs: Gate fully surrounds the channel, improving electrostatic control and enabling continued scaling beyond 3 nm.

3D and Vertical FETs: Fully stacked or vertically oriented devices (VFETs, 3DS-FETs, MBC-FETs) aim to maximize density while minimizing footprint.

Example:

Scaling efficiency improves as gate control strengthens, reducing drain capacitance and improving short-channel effects.

6. Design-Technology Co-Optimization (DTCO and STCO)
DTCO:

Co-develops circuit layout rules and device technology simultaneously.

Innovations include backside interconnects, buried power rails, and standard cell co-design, enabling compact layouts and lower resistance paths.

STCO:

Extends co-optimization beyond single chips—focuses on multi-die integration and chiplet design for modular scalability.

Heterogeneous chiplets allow mixing of specialized dies (CPU, AI, I/O) with varying process technologies for better efficiency and flexibility.

Together, DTCO and STCO form the ecosystem strategy for sub-1 nm nodes: pushing co-design from transistor scale to system scale.

7. FEOL Innovations and Technological Inflection Points
FEOL (Front-End of Line):
Covers everything until the first metal layer—transistor formation, dopant implantation, strain engineering, and isolation structures.

Key Node Innovations:

Technology Node	Major Innovation	Impact
180 nm	Voltage scaling	Lower power operation
130 nm	Copper BEOL	Reduced RC delay
90 nm	Uniaxial strained Si	Enhanced NMOS performance
65 nm	Embedded SiGe	Enhanced PMOS transport
45 nm	HKMG	Reduced leakage, better gate control
32 nm	Raised S/D regions	Improved current drive
These inflection points demonstrate how every scaling generation required material and process breakthroughs, not just shrinking geometries.

8. CMOS Evolution Toward and Beyond the 1 nm Era
Transition from scaling to innovation:

Classical Dennard scaling (power density constant) has broken down, leading to the “power wall.”

Future scaling involves material, architecture, and system-level rethinking rather than pure geometric shrinkage.

Emerging trends include hybrid CMOS-non-CMOS computing: spintronics, ferroelectric memories (FeFETs), and neuromorphic architectures.

9. Broader Perspective: From FinFET to Zettascale
The continued evolution of transistor design—FinFET to GAA to vertical 3D structures—underpins the hardware infrastructure enabling exascale and, eventually, zettascale computing.
Each transistor architecture contributes incremental efficiency gains that, when scaled across billions of devices, define the trajectory of computational capability per watt.

This topic provides a detailed continuum of CMOS node evolution—from 22 nm FinFET introduction to sub-1 nm CFET and 2D-material-based FET architectures—highlighting both structural innovations and material challenges that define each generation. Here’s a structured technical summary to tie all these together with performance and process insights.
1. Evolution of Key Technology Nodes
| Node                             | Key Innovations                                                                                   | Purpose/Impact                                                                     |
| -------------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| 22 nm (2011–2012)                | FinFET (Tri-Gate) introduction, Self-Aligned Contacts (SAC), Copper interconnects (Co+Cu BEOL)    | Solved planar leakage limits; better electrostatic control; start of 3D device era |
| 14 nm (2014–2015)                | Unidirectional metal routing, SADP (Self-Aligned Double Patterning), SDB (Single Diffusion Break) | Improved pattern fidelity and density; tighter layout rules                        |
| 10 nm (2017)                     | SA-SDB (Self-Aligned SDB), LELELE, SAQP (Self-Aligned Quadruple Patterning)                       | Enabled extreme feature scaling before EUV readiness                               |
| 7 nm (2019)                      | First widespread EUV lithography use                                                              | Reduced multi-patterning complexity and overlay errors                             |
| 5 nm (2020)                      | SiGe channels for PMOS, EUV SA-LELE hybrid                                                        | Enhanced hole mobility; reduced power and increased transistor current             |
| 3 nm / 2 nm / 1.4 nm (2023–2026) | Gate-All-Around (GAA) nanosheet FETs                                                              | Full gate wrap improves channel control and scaling beyond FinFET limits           |
| Sub-1 nm (2030+)                 | CFET (Complementary FET), 2D FETs using MoS₂, WS₂                                                 | Leverages vertical stacking and monolayer channels to continue Moore’s Law         |

2. Fin Depopulation and Density Scaling (Samsung’s Example)
In FinFET designs, transistor drive current and area efficiency depend on fin number and height. “Fin depopulation” reduces the number of fins per transistor while keeping fin width and pitch fixed, enabling denser layouts.
| Node  | Fin Height | Fins per Device | Process Class | Trend                                                   |
| ----- | ---------- | --------------- | ------------- | ------------------------------------------------------- |
| 10 nm | 420 nm     | 10              | HD            | Baseline                                                |
| 8 nm  | 378 nm     | 9               | UHD           | Slight reduction                                        |
| 7 nm  | 27 nm      | 8               | HD            | Transition to EUV-ready scaling                         |
| 5 nm  | 27 nm      | 7               | UHD           | Optimized for smaller cell height and lower capacitance |
This controlled depopulation maintains transistor performance while increasing integration density.

3. Diffusion Break and Contact Innovations
These techniques address layout compaction and isolation in dense standard-cell architectures.

Double Diffusion Break (DDB): Creates an insulating region between source and drain diffusion areas, minimizing leakage and enabling ultra-small cells.

Single Diffusion Break (SDB): Less aggressive—adds isolation on one side, trading off compactness for simplicity.

Contact Over Field Gate (COFG): Places gate contact over the STI (field oxide) to shrink layout width.

Contact Over Active Gate (COAG): Positions contact directly above the gate; allows maximum density in latest FinFET and GAA designs.

Backside Power Delivery Network (BS-PDN): Routes power on the wafer backside to free frontside space for signal routing and logic transistors; improves IR drop and reduces resistance.

These enable 3D-aware layout styles (buried rails, BSI) used in sub-3 nm designs.

4. Device Architecture Transitions:
| Device Type              | Gate/Channel Structure   | Control Efficiency | WC/WGW_C/W_GWC/WG | REXT/RchR_{EXT}/R_{ch}REXT/Rch | Remarks                                     |
| ------------------------ | ------------------------ | ------------------ | ----------------- | ------------------------------ | ------------------------------------------- |
| Planar MOS               | 1-sided flat gate        | Low                | 1                 | < 1                            | Minimal parasitic resistance                |
| FinFET                   | Gate on 3 sides          | Medium-high        | ≈ 1/3             | ≈ 1                            | Balanced performance-density tradeoff       |
| GAA (Nanosheet/Nanowire) | Gate all around          | Very high          | ≈ 1/6             | ≈ 3                            | Best electrostatics, high parasitic         |
| CFET                     | Vertical NMOS+PMOS stack | Excellent          | ≈ 1/6             | ≈ 3                            | Doubles density, same parasitic bottlenecks |
Lesson: As gates wrap more completely around channels, electrostatic control improves but parasitic resistance escalates due to smaller contact/fringe areas.

5. Parasitic Resistance Breakdown and Optimization
Parasitic resistance becomes a growing performance barrier as transistor dimensions shrink.
nitial vs. Improved Reduction Trends:

NFET:contribution reduced from 63% → 48% through advanced contact metals and doped interfaces.

PFET: ortion reduced from 50% → 22% by epitaxial stress and S/D engineering.
6. Variability and Voltage Control Across Eras
| Technology                        | TypicalVtV_tVtVariability | Key Factor                                        |
| --------------------------------- | ------------------------- | ------------------------------------------------- |
| Planar MOSFET (100 nm+)           | ≈ 130 mV                  | Random dopant and oxide thickness fluctuation     |
| FinFET (~22 nm)                   | ≈ 14 mV                   | 3D geometry, better electrostatics                |
| Nanowire / GAA (~14 nm and below) | ≈ 7 mV                    | Quantum confinement and tight dimensional control |
Reduced Vt variability stabilizes performance and leakage across large transistor populations—crucial for AI and HPC workloads.
7. Toward the Sub-1 nm Era
CFET Integration: Vertical NMOS–PMOS stacking reduces footprint by ~50%, saving routing space.

2D FETs (e.g., MoS₂, WSe₂): Atomic-scale channels (<1 nm thick) allow scaling without mobility loss.

Backside Contacts + BS-PDN: Enable vertical current flow and decoupled signal/power paths.

Challenges: Managing contact resistance, alignment tolerance, and atomic interface reliability.

8. Summary of Evolution Trends
| Aspect           | Evolution Path               | Scaling Emphasis        |
| ---------------- | ---------------------------- | ----------------------- |
| Channel Material | Si → SiGe → 2D (MoS₂, WSe₂)  | Mobility and leakage    |
| Lithography      | DUV → EUV → High-NA EUV      | Pattern precision       |
| Architecture     | Planar → FinFET → GAA → CFET | Density and control     |
| Interconnect     | Cu → Co/Ru/BSI               | Resistivity and IR drop |
| Co-Optimization  | DTCO → STCO                  | Design-device alignment |
This section captures the frontier of nanoscale CMOS device scaling—from 22 nm node parasitic capacitance engineering to all‑2D transistor architectures nearing the 1 nm regime. Each concept reflects the convergence of materials science, fabrication strategy, and device physics for sustaining Moore’s Law beyond traditional silicon. Below is a comprehensive, structured breakdown.

1. Effective Capacitance (Cₑff) Evolution from 22 nm to 7 nm
Observation: As CMOS nodes shrink, parasitic capacitances increasingly dominate transistor delay and power consumption.
| Node  | Major Contributor                | Description                                                                                                |
| ----- | -------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| 22 nm | Fringing capacitance (Cfr = 56%) | Field coupling between gate and contact dominated total Cₑff; intrinsic gate capacitance smaller share.    |
| 14 nm | Cfr drops to 38%, Cpc‑ca rises   | Parasitic between contact and channel began limiting delay more than intrinsic factors.                    |
| 10 nm | Cfr = 25%, Cpc‑ca dominates      | Shrinking geometries increased coupling between contacts and local interconnects.                          |
| 7 nm  | Gate capacitance (Cg ≈ 45%)      | Transition: electrostatic gate control becomes dominant factor due to thinner oxides and shorter channels. |
Implication: Parasitic control—not channel scaling—became the bottleneck after 14 nm. Improving dielectric isolation, spacer materials, and contact layouts are critical.

2. Spacer Engineering and Cₑff Reduction
Experimental Evidence:

Using SiBCN spacers (instead of SiN) yields:

8% Cₑff reduction.

Direct 8–10% ring‑oscillator delay reduction, confirming lower parasitic load.

Transition in spacer materials:

SiOCN (legacy) → SiCO (low‑k) → Air‑gap spacers (k ≈ 1).

Air spacers demonstrated ≈15% Cₑff reduction, pushing delay and power envelopes lower.

Conclusion: Spacer dielectric engineering is central to FEOL optimization. Air or low‑k cavities around the gate significantly decouple parasitic elements—especially crucial for GAA structures with dense gate spacing.

3. 2D Channel Material Advantages (MoS₂ Example)
4. | Property              | MoS₂                        | Silicon (Si)      | Advantage                                             |
| --------------------- | --------------------------- | ----------------- | ----------------------------------------------------- |
| Monolayer thickness   | ~0.65 nm                    | ~3–5 nm (channel) | Ideal atomic‑scale thickness for sub‑1 nm devices.    |
| Effective massm∗m^*m∗ | 0.55 m₀                     | 0.22 m₀           | Higher mass suppresses tunneling leakage.             |
| Bandgap               | ~1.85 eV (1L), ~1.5 eV (2L) | 1.12 eV           | Wide gap reduces off‑current and leakage.             |
| Dielectric constant   | Low (~3–5)                  | ~11.9             | ImprovesCD/CoxC_D/C_{ox}CD/Coxratio for gate control. |

4. Direct Source‑to‑Drain Tunneling Physics
As gate length Lg shrinks below ~5 nm, potential barriers thin enough for quantum tunneling cause leakage.
Leakage I SD,leak
  scales with:Increasing m* and Egexponentially reduces leakage.

MoS₂ exhibits >100× leakage reduction at 1 nm nodes versus silicon.

This explains why transition metal dichalcogenides (TMDs) are leading post‑Si channel candidates.
5. Breakthrough MoS₂ Transistor at 1 nm Gate Length
Design Summary:

Channel: Monolayer MoS₂.

Gate: Single‑walled carbon nanotube (SWCNT) – acts as 1 nm gate electrode.

Dielectric: ZrO₂ (high‑k).

Substrate: SiO₂ atop n⁺ Si back‑gate.

Key Outcomes:

Exceptional electrostatic control at 1 nm due to cylindrical CNT gate.

Low leakage and scalable subthreshold slope (<70 mV/dec).

Proof that physical gate control can persist even at atomic length scales.
6. All‑2D MOSFET Architecture and Fabrication:
| Layer             | Material | Function                                  |
| ----------------- | -------- | ----------------------------------------- |
| Source/Drain/Gate | Graphene | Ultra‑conductive 2D contact electrode     |
| Channel           | MoS₂     | 2D semiconductor for switching            |
| Dielectric        | h‑BN     | 2D insulator; atomically sharp interfaces |
| Substrate         | Si/SiO₂  | Mechanical support; optional back‑gate    |
Fabrication Steps:

Deposit graphene on SiO₂ as gate.

Pattern graphene for S/D regions.

Transfer MoS₂ layer for channel.

Overlay h‑BN dielectric.

Add graphene top gate and metal contacts (Ni/Au).
7. Non‑Planar and Monolithic 3D CMOS Integration
Challenges:
Growing single‑crystal semiconductors on 3D surfaces is difficult due to lattice mismatch and roughness.

Architectures:

Single‑Layer CMOS: NMOS and PMOS share one silicon plane; lateral interconnections consume large area.

Monolithic 3D CMOS: NMOS (bottom) and PMOS (top) stacked vertically with oxide isolation. Shorter interconnects reduce delay and area, improving energy efficiency.

Logic Example:

Traditional planar inverter uses horizontal routing.

3D inverter integrates through‑oxide vias, cutting interconnect delay significantly.

Implication:
Monolithic 3D and CFET concepts converge—both aim to vertically integrate complementary devices, advancing beyond 2D chip layouts.

8. Summary of the Scaling Transition Path:
| Domain          | 22 nm → 7 nm             | Beyond 7 nm to 1 nm        | Post‑1 nm                               |
| --------------- | ------------------------ | -------------------------- | --------------------------------------- |
| Dielectrics     | SiN → SiBCN → Air spacer | Ultra‑low k + air cavities | 2D material isolation                   |
| Channel         | Si → SiGe                | 2D MoS₂, WS₂               | All‑2D integration                      |
| Structure       | FinFET → GAA             | CFET, 3D stacking          | Monolithic 3D logic                     |
| Leakage Control | Strain + HKMG            | Quantum‑confined TMDs      | Quantum/2D tunneling FETs               |
| Integration     | DTCO                     | STCO                       | System‑scale chiplet/hetero integration |
Here’s a clear technical summary linking advanced interconnect scaling challenges and solutions with OpenROAD physical design automation—including stepwise setup instructions and configuration for a custom ASIC using the Sky130hd platform.

Interconnect Scaling: Cu, Ru, and Barriers
7nm Dual Damascene Cu:

Combines vias and lines in one patterning step, using copper for both vertical (vias) and horizontal (lines) interconnects.

Challenges: As pitch shrinks to 36 nm, voids and copper reliability issues arise due to gap-filling difficulties and electromigration risks.

5nm Single Damascene Cu:

Splits via and line formation into separate steps, optimizing gap-fill and resistance for a tighter 28 nm pitch.

Focus: Minimize resistance in narrow wires and tiny vias for performance at small geometries.

3nm Barrier Optimization:

Thinner barrier metals (e.g., TaN by ALD) minimize series resistance, crucial at pitch ≤ 24 nm.

This step enables robust, low-resistance via connections and reduces overall interconnect parasitics.

Sub-18nm Advanced Metals:

Introduction of subtractive RIE for precise patterning, and alternative conductors like ruthenium (Ru) with superior reliability below 15 nm.

Tall, barrier-less designs (“post-Damascene”) eliminate conventional lining for further reduction in electromigration and resistance.

Key Concept:
Atomic layer barriers (TaN) are used to block copper diffusion, deposited by ALD for maximum conformity; process is crucial for maintaining interconnect reliability as feature sizes shrink.

Back-Side Power Delivery Network (BS-PDN)
BS-PDN routes power lines on the chip’s backside, enabling:

Shorter, wider wires for lower IR drop.

Higher density and smaller standard cell area.

Increased switching speed and reduced power dissipation.

Benefits:

Reduces supply voltage variation (enhancing timing closure).

Allows aggressive logic packing while maintaining robust power rails—a modern necessity for AI/HPC-grade ASICs.

OpenROAD Flow for VSDBabySoC (Sky130hd)
1. Preparation Steps
Clone the OpenROAD scripts repository:
``` bash
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts
cd OpenROAD-flow-scripts
sudo ./setup.sh ./build_openroad.sh --local
source ./env.sh
yosys -help
openroad -help
cd flow
```
2. Project Directory Structure
Create vsdbabysoc inside:

OpenROAD-flow-scripts/flow/designs/sky130hd
OpenROAD-flow-scripts/flow/designs/src

Add Verilog design files to src/vsdbabysoc.
Copy .gds, .lef, .lib IP/macros into respective folders within sky130hd/vsdbabysoc.
Add constraints (vsdbabysoc_synthesis.sdc), pin/macro configuration files (macro.cfg, pin_order.cfg).
