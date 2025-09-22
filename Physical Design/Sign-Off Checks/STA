What is STA?

Static Timing Analysis (STA) is a method to verify timing of a digital design (like an SoC) without simulating input vectors. Instead of running dynamic simulations, it uses constraints (clock, delay, process, etc.) and checks whether all signal paths meet setup and hold timing requirements across all corners and modes.

Why STA in SoCs?

Modern SoCs are:
 • Multi-million (sometimes billion) gate designs.
 • Have multiple voltage domains, clock domains, and power states.
 • Must work reliably across Process, Voltage, and Temperature (PVT) variations.

STA ensures:
 • The design meets timing across all functional modes (functional, scan, low power, etc.).
 • Timing closure before fabrication → avoiding costly re-spins.

Key Concepts in STA for SoCs

1. Timing Paths

Every data transfer path in STA is broken into 3 parts:
 • Launch point → usually a flip-flop, latch, or input port.
 • Combinational logic → gates, muxes, interconnect.
 • Capture point → flip-flop, latch, or output port.

Two major checks:
 • Setup check → Data arrives before the capturing clock edge.
 • Hold check → Data is stable for some time after the clock edge.

2. Clocks & Constraints
 • Defined in SDC (Synopsys Design Constraints) format.
 • Multiple clock domains with interactions (synchronous, asynchronous, generated clocks).
 • Clock uncertainty, jitter, and skew must be modeled.

3. Corners and Modes
 • Corners → PVT variations (SS, FF, TT, voltage ±10%, temp extremes).
 • Modes → Functional, scan test, low-power, sleep, etc.
 • Multi-Mode Multi-Corner (MMMC) STA is essential for SoCs.

4. On-Chip Variation (OCV)
 • Accounts for process variation across the chip.
 • Variants: AOCV (Advanced OCV), POCV (Parametric OCV).

5. Special Timing Scenarios
 • Clock Domain Crossing (CDC) → Need synchronizers, false-path constraints.
 • Asynchronous Interfaces → Must declare false/multicycle paths.
 • Level Shifters / Voltage Islands → Extra delay modeling.
 • DFT (Scan, BIST) → Additional scan mode timing checks.

6. Tools
 • Industry standard → Synopsys PrimeTime, Cadence Tempus, ANSYS PathFinder (for reliability + STA).

STA Flow in SoCs
 1. Netlist + parasitics (post-layout).
 2. Read libraries (timing models at different PVT corners).
 3. Read SDC constraints (clocks, I/O delays, exceptions).
 4. Run timing analysis across MMMC views.
 5. Check timing reports (setup, hold, recovery, removal, pulse width).
 6. Close timing → fix violations via:
 • Buffer insertion / resizing
 • Gate-level optimization
 • Placement/routing fixes
 • Clock tree adjustments

STA Challenges in Modern SoCs
 • Hundreds of modes and corners → analysis runtime explosion.
 • Clock interactions in large SoCs with multiple PLLs.
 • Power-aware STA (low power design with power gating, retention).
 • Sign-off correlation with silicon.

STA in SoCs ensures the chip meets timing in all operating conditions (modes, corners, domains) before tape-out. It’s the backbone of digital design sign-off.
