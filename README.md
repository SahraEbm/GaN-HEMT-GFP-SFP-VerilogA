# GaN HEMT with Gate and Source Field Plates Compact Model (Verilog-A)

## Overview

This repository presents a **physics-based, modular Verilog-A compact model** for **AlGaN/GaN High Electron Mobility Transistors (HEMTs)** incorporating both **Gate Field Plate (GFP)** and **Source Field Plate (SFP)** structures. The model has been developed within the framework of a collaborative research effort between Amirkabir University of Technology (AUT) and the École Polytechnique Fédérale de Lausanne (EPFL), building upon advanced EPFL-style HEMT modeling methodologies.

Designed for high-accuracy circuit simulation in **power electronics** and **RF/microwave applications**, the model integrates intrinsic device physics, dual field-plate electrostatic effects, extrinsic parasitics, and critical second-order phenomena essential for predictive modeling of modern GaN power and RF devices.

---

## Key Features

The compact model incorporates a comprehensive set of electro-thermal and high-field physical mechanisms:

### Intrinsic Channel Physics
- Charge-based core current formulation
- Velocity saturation and mobility degradation
- Bias-dependent transconductance and output conductance

### Advanced Dual Field-Plate Modeling (GFP + SFP)
- Coupled electrostatic modulation from gate and source field plates
- Effective redistribution and dual suppression of peak electric fields
- Significant enhancement of breakdown voltage
- Improved control of surface potential and reduction of current collapse

### Secondary Physical Effects
- Self-heating via thermal RC network
- Charge trapping and dynamic current collapse
- Buffer leakage and high-field tunneling (GIDL/GISL)
- Nonlinear voltage-dependent capacitances (Cgs, Cgd, Cgb)
- Geometry-dependent fringing capacitances

### Extrinsic Parasitics
- Bias- and geometry-dependent source/drain access resistances
- Temperature scaling of resistances
- Gate resistance for RF applications
- Overlap and parasitic capacitances

---
Physical Modeling Approach
The model is grounded in a surface-potential / charge-based framework with physics-based extensions for dual field-plate structures. It accounts for the complex interaction between gate- and source-connected field plates, providing accurate prediction of electric field distribution, breakdown characteristics, and dynamic device behavior under both DC and large-signal operation.

Parameter Extraction Methodology
Parameters are extracted using a systematic hierarchical approach combining DC, pulsed, small-signal, and thermal measurements.

Dual Field-Plate Modeling (Key Contribution)
The combined implementation of Gate and Source Field Plates enables superior electric field management, resulting in:

Higher breakdown voltage
Reduced dynamic on-resistance (current collapse)
Improved RF power performance and linearity
Better overall device reliability


Validation
The model has been validated against experimental and TCAD data covering:

DC and pulsed I–V characteristics
Capacitance–voltage profiling
Small-signal RF parameters
Breakdown voltage behavior


Python Calibration Framework
A complete Python-based workflow is provided for parameter extraction, optimization, and model validation.

Citation
If you use this model in your research or publications, please cite:
S. Ebrahimmagham et al., "Compact Verilog-A Model for GaN HEMTs with Gate and Source Field Plates," Amirkabir University of Technology (AUT) and École Polytechnique Fédérale de Lausanne (EPFL), 2026.

License
This project is released under the MIT License.
See the LICENSE file for details.

Authors & Collaboration
This work is the result of a collaborative research project between:

Amirkabir University of Technology (AUT), Tehran, Iran
École Polytechnique Fédérale de Lausanne (EPFL), Lausanne, Switzerland

Authors

Sahra Ebrahimmagham (Researcher, AUT)

Dr. Majid Shalchian (Assistant Professor, AUT)

Dr. Farzan Jazaeri (Researcher, EPFL)


Contact
For inquiries, collaboration opportunities, or industrial licensing:

GitHub: SahraEbm

Email: sahra.ebm@gmail.com


Acknowledgments
The development of this model greatly benefited from the advanced compact modeling expertise at EPFL and the strong research environment at AUT in the field of wide-bandgap semiconductor devices.
Simulator Compatibility

Cadence Spectre
Keysight ADS
Synopsys HSPICE / PrimeSim (Verilog-A)

## Model Architecture

The implementation follows a clean, modular Verilog-A structure that facilitates independent calibration and extension of individual physical modules.

```text
GaN-HEMT-GSFP-Model/
│
├── src/
│   ├── hemt_core_channel.va
│   ├── hemt_gate_field_plate.va
│   ├── hemt_source_field_plate.va
│   ├── hemt_self_heating.va
│   ├── hemt_trapping_current_collapse.va
│   ├── hemt_gidl_gisl_leakage.va
│   ├── hemt_fringing_capacitances.va
│   ├── hemt_extrinsic_resistances.va
│   ├── hemt_overlap_capacitances.va
│   └── hemt_top.va
│
├── testbenches/
│   ├── dc_iv_simulation.va
│   ├── cv_characterization.va
│   ├── pulsed_iv_simulation.va
│   └── rf_s_parameters.va
│
├── python/
│   ├── parameter_extraction.py
│   ├── model_validation.py
│   └── fit_trapping_model.py
│
├── docs/
│   ├── parameter_extraction_guide.md
│   ├── model_theory.pdf
│   └── figures/
│
├── LICENSE
├── CITATION.cff
└── README.md


