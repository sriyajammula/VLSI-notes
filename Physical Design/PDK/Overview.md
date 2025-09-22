What is a PDK?

PDK = Process Design Kit.
It is a collection of files, models, and rules provided by a semiconductor foundry (TSMC, Samsung, Intel, GF, etc.) that describe how their fabrication process works.

Think of it as the “bridge” between semiconductor manufacturing and chip design tools (EDA).
 • Foundry → defines the physics, materials, and device characteristics.
 • Designers → need this data inside CAD tools to create standard cells, IPs, and SoCs.
 • PDK = packaged knowledge of the process, usable in design flow.

⸻

What is inside a PDK?

A PDK usually contains:
 1. Design rules
 • DRC (Design Rule Check) – min width/spacing, enclosure, antenna rules, etc.
 • LVS (Layout vs. Schematic) – device recognition rules.
 • ERC/DFM checks.
 2. Device models
 • SPICE models (transistors, diodes, resistors, capacitors).
 • Corner models (TT, SS, FF, SF, FS for process variations).
 • Parasitic models (RC extraction decks).
 3. Technology files
 • Layer definitions (metal stack, vias, diffusion, poly).
 • Process stack information for layout tools.
 4. Standard cell/IP views (sometimes included separately as a library)
 • Liberty (.lib) timing and power data.
 • LEF/DEF abstract views for PnR.
 • GDS/OASIS layout data.

⸻

Why is PDK useful for SoC/IP Design?

When designing SoC or IP, you need to ensure your design is fabricatable in the target technology node (e.g., 5nm, 16nm, 28nm). PDK makes this possible by:
 1. Accuracy in Simulation
 • Provides foundry-calibrated transistor models for SPICE/analog simulations.
 • Enables accurate timing, power, and noise simulations for digital flows.
 2. Physical Verification
 • DRC/LVS decks ensure your layout follows foundry’s rules.
 • Prevents yield loss and fabrication errors.
 3. Standardization
 • Ensures that all design teams (analog, digital, mixed-signal, IP vendors) work with the same process definitions.
 • Makes IP portable across SoC projects in the same technology node.
 4. IP Integration
 • Provides abstract views for IP blocks (LEF/lib) so they can be cleanly integrated into SoC PnR.
 5. Manufacturability & Yield
 • Includes DFM (Design for Manufacturability) rules.
 • Helps designers avoid systematic yield problems.

⸻

✅ In short:
A PDK is the recipe book for a semiconductor process. Without it, you can’t reliably design or tape out an SoC/IP. It ensures your design matches the physics of the foundry process and is manufacturable with good yield.
