# README.md

## Project Title: Cross-Verification of Power Results — Manual Calculations vs. Voltus Output

### Author: Ishaan Singhal  
### Date: July 12, 2025 (Done while in summer intern from June- August)

## Overview

This comprehensive project involves an in-depth cross-verification of power analysis results for a digital circuit design. I extensively utilized Cadence Voltus software to generate detailed power metrics, including leakage, switching, and internal power, and rigorously compared them against meticulous manual calculations. The goal was to validate the accuracy of Voltus outputs by cross-referencing with hand-computed values derived from library files and other design artifacts. This involved a thorough analysis of multiple file types, extensive data processing, and iterative verification steps to ensure precision and reliability.

Through this project, I demonstrated a deep dive into power estimation methodologies, highlighting discrepancies, performing percentage error calculations, and providing actionable insights for digital design optimization. The work encompassed running simulations, parsing reports, normalizing data, and documenting every step with high attention to detail.

## Project Scope and Extensive Work Performed

I invested significant effort into this project, going above and beyond to ensure a robust verification process. Here's a detailed breakdown of the extensive tasks I completed:

- **Setup and Data Acquisition:** I started by thoroughly reviewing and utilizing the provided RAK (Reference Application Kit) files for Cadence Voltus. This included extracting and analyzing key components such as the `.lib` (library) files, which contain critical cell characterization data for power, timing, and capacitance.
  
- **Design Execution in Voltus:** I ran the full design flow using the slow corner library (slow lib) as specified in the accompanying PPT. This involved loading the design, configuring the environment, and executing power analysis simulations to generate comprehensive reports on leakage power, switching power, and internal power. I meticulously tuned parameters like supply voltage (VDD), clock frequency, and switching activities to match real-world scenarios.

- **Manual Calculations:** In parallel, I performed exhaustive manual computations for all power components. These were derived directly from the `.lib` file within the Voltus RAK. I studied and extracted values for load capacitance (Cl), switching activity (α), rise/fall energies, and more. Calculations were done step-by-step, incorporating formulas for switching power (P = α × Cl × VDD² × f) and internal power based on averaged energies and activity factors. I also normalized slew rates between bounds (e.g., 20-80) for consistency.

- **File Analysis and Cross-Referencing:** To enhance accuracy, I simultaneously analyzed additional design files such as LEF (Library Exchange Format) for physical cell layouts, DEF (Design Exchange Format) for placement and routing details, and other supporting artifacts. This multi-file analysis allowed me to validate assumptions, identify potential mismatches in capacitance or transition models, and refine my calculations iteratively.


- **Documentation and Iteration:** I iterated multiple times on the calculations to minimize errors, documented everything in a PPT with visuals and tables, and even rated the project internally for self-assessment.

## Contents

- `Voltus-Project.pptx` — Main presentation containing:
  - Power calculation methodology
  - Step-by-step manual computation
  - Voltus output data
  - Slew normalization process
  - Tabulated results and final power summary
- `inst_pwr.rpt` — Saved Voltus power report for reference.

## Methodology

### 1. Saving Voltus Report
- The Voltus power report is saved in the file format: `inst_pwr.rpt`.

### 2. Units
- All power values are calculated and reported in microWatts (μW) or milliWatts (mW) as specified in the `.lib` file.

### 3. Power Components

#### Leakage Power
- Directly obtained from Voltus output.

#### Switching Power
- Calculated using the formula:  
  \( P = \alpha \times C_l \times V_{DD}^2 \times f \)
  - \( \alpha \): Switching Activity
  - \( C_l \): Load Capacitance
  - \( V_{DD} \): Supply Voltage
  - \( f \): Clock Frequency

#### Internal Power
- Computed for various input-output transitions using average rise/fall energies and activity factors.

#### Slew Normalization
- Slew values are normalized between upper (80) and lower (20) bounds for consistent comparison.

## Example Calculations

### Switching Power (Manual Calculation)
- Example:  
  \( 0.5 \times (0.00595853 \times 10^{-9}) \times (0.9^2) \times 2 = 0.6033 \ \mu W \)

### Internal Power (Manual Calculation)
- Example:  
  - Rise/Fall energies averaged over measurements
  - Internal Power = (activity/ns) × (weight × energy)

## Results Summary

| Power Component      | Value                        |
|----------------------|-----------------------------|
| Leakage Power        | 0.00006704 mW               |
| Total Switching Power| 1.0471159625 μW             |
| Total Internal Power | 22.8148212046 × 10⁻⁸ W      |
| **Total Power (Manual)**   | 0.00037138539688273736 mW   |
| **Total Power (Voltus)**   | 0.0039810 mW                 |

## How to Use

1. Review the `Voltus-Project.pptx` for detailed step-by-step calculations and results.
2. Refer to tabulated data for direct comparison between manual and Voltus results.
3. Use the provided formulas and normalization techniques to replicate or verify calculations for similar projects.

## Suggestions for GitHub Repo

To make your GitHub repository more professional and complete, consider adding the following:

- **Scripts and Code:** Include any TCL scripts used for Voltus automation, or Python scripts for parsing reports and calculating errors.
- **Additional Documentation:** Add a `CONTRIBUTING.md` for collaboration guidelines, and a `LICENSE` file (e.g., MIT) for open-source sharing.
- **Data Files:** Upload sample `.lib`, LEF, DEF files (anonymized if sensitive), and the full Voltus report.
- **Visuals:** Include screenshots or diagrams from the PPT as image files in a `images/` folder.
- **Changelog:** A `CHANGELOG.md` to track updates, like error investigations or methodology refinements.
- **README Enhancements:** Embed badges for build status, license, or stars if applicable.

## Notes

- All calculations are based on values and outputs from the specified Voltus report and the provided `.lib` file.
- Slew normalization and energy averaging are crucial for accurate internal power estimation.
- The methodology can be adapted for other digital design power verification tasks.
- 
## Due to privacy concerns of Cadence, the .lib files and generated .rpt files are on the virtual machine and cannot be shared anywhere else. 
