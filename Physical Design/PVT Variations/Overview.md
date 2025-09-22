PVT variations-
1) Process (P)
 • Process variation = run-to-run, die-to-die and within-die (local) variations in device geometry, doping, oxide thickness
 • Geometrical variations (L, W): up to ~±2–10% depending on node and feature (patterning, OPC).
 • Threshold voltage (Vth) / drive current (Ion): variability can be up to ~±5–10%
Effect -
 • Delay spread, timing failures, SRAM stability (Vmin), increased leakage (for some corners), lower yield.
 • Within-die mismatch affects analog matching, SRAM bitcell failure, and critical paths.
Mitigation-
 1. Statistical timing + variation-aware sign-off (Monte-Carlo, SSTA) — design to statistical yield 
 2. Adaptive Body Bias (ABB) / Static Body Bias (SBB) — shift Vth per-die or per-block to recover speed or cut leakage. 
 3. Design margins & conservative corners — guardbanding 
 4. Sizing & redundancy — upsizing transistors on critical paths; spare rows/columns and ECC for memories.
 5. Layout techniques for matching — common-centroid, interdigitation, dummy fingers 
 6. Process control & calibration — on-chip sensors (ring oscillators, corner detectors) + post-silicon calibration (voltage trim).
 7. Variation-tolerant circuit styles — error detection/recovery , differential signaling
2) Voltage (V)
 • (I/O, analog) ±5%; core rails ~±1–3% . Transient droops during switching can be (tens of mV). 
 • Transient droop (IR drop + decoupling limits) can cause VDD reductions of several % to >10%
Effect-
 • Delay is sensitive to VDD near Vth: small % change in VDD → larger % change in delay. 
 • Lower VDD increases delay and higher VDD increases leakage and stress.
Mitigation-
 1. Robust power-grid & decoupling 
 2. Fast local regulators / LDOs / point-of-load converters 
 3. Dynamic Voltage and Frequency Scaling (DVFS) with margining 
 4. OCV (on-chip variation) and timing monitors (Razor, canaries) that trigger corrective action (voltage bump or clock slow-down).
 5. Power aware synthesis / floorplanning
3) Temperature (T)
 • Chips operation-consumer ~−40°C to +85°C; industrial/automotive up to +125°C or more. On-chip hotspot delta from ambient can be 20–60°C 
 • parameters (mobility, leakage, bandgap) depend on T — mobility decreases with increasing T (leakage/subthreshold current increases with T. Mobility and resistivity changes are of a few % to tens of % 
Effect -
 • higher T → slower carrier mobility → longer delay, but there are cases of temperature inversion (delay decreases with temperature in some corners near threshold because Vth shifts dominate). Leakage increases strongly with T (exponential).
 • Large ΔT across chip causes frequency variations and potential hot-spot induced failures.
Mitigation-
 1. Thermal management — heat sinks, active cooling, airflow, PCB thermal vias.
 2. On-chip temperature sensors & dynamic thermal management (DTM) — throttle frequency, migrate workload, DVFS 
 3. Place sensitive circuits away from hot blocks
 4. Worst-case sign-off + silicon monitoring
