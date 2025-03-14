# Project: Analysis of Voltage Transfer Characteristic (VTC) and Power Dissipation in a CMOS Inverter using LTspice

## Overview
This project focuses on analyzing the **Voltage Transfer Characteristic (VTC)** and **Power Dissipation** of a CMOS inverter using **LTspice**. The CMOS inverter is a fundamental building block in digital circuits, and understanding its behavior is crucial for designing energy-efficient and high-performance systems. The project involves:
1. Simulating the VTC curve to study the input-output relationship.
2. Analyzing static and dynamic power dissipation.
3. Using Level 3 SPICE models for NMOS and PMOS transistors.
![Screenshot 2025-03-14 234303](https://github.com/user-attachments/assets/708a102b-2142-4c10-97f1-1b582866e0d3)


---

## Table of Contents
1. [Project Description](#project-description)
2. [Circuit Design](#circuit-design)
3. [Simulation Setup](#simulation-setup)
4. [Results](#results)
5. [Usage](#usage)
6. [References](#references)
7. [License](#license)

---

## Project Description
The CMOS inverter consists of an NMOS and a PMOS transistor. The project aims to:
- **Simulate the VTC curve**: Analyze the relationship between input voltage (\(V_{in}\)) and output voltage (\(V_{out}\)).
- **Measure power dissipation**: Evaluate static and dynamic power consumption.
- **Optimize performance**: Study the impact of transistor parameters on circuit behavior.

The project uses **LTspice**, a powerful SPICE-based circuit simulator, to perform DC and transient analyses.

---

## Circuit Design
The CMOS inverter circuit is designed using the following components:
- **NMOS Transistor**: Level 3 SPICE model with parameters such as \(V_{th,n}\), \(KP_n\), and \(\lambda_n\).
- **PMOS Transistor**: Level 3 SPICE model with parameters such as \(V_{th,p}\), \(KP_p\), and \(\lambda_p\).
- **Power Supply (\(V_{DD}\))**: Typically set to 5V.
- **Load Capacitance (\(C_L\))**: Represents the output load.

### SPICE Models
```spice
.MODEL NMOS NMOS LEVEL=3 TOX=200E-10 PHI=0.7 UO=650 KP=120E-6 RSH=0 XJ=500E-9 
+ CGDO=200E-12 CJ=400E-6 CJSW=300E-12 NSUB=1E17 VTO=1 ETA=3.0E-6 VMAX=1E5 NFS=1E12 
+ LD=100E-9 CGSO=200E-12 PB=1 MJSW=0.5 GAMMA=0 DELTA=3.0 THETA=0.1 KAPPA=0.3 TPG=1 
+ CGBO=1E-10 MJ=0.5

.MODEL PMOS PMOS LEVEL=3 TOX=200E-10 PHI=0.7 UO=250 KP=40E-6 RSH=0 XJ=500E-9 
+ CGDO=200E-12 CJ=400E-6 CJSW=300E-12 NSUB=1E17 VTO=-1 ETA=0 VMAX=5E4 NFS=1E12 
+ LD=100E-9 CGSO=200E-12 PB=1 MJSW=0.5 GAMMA=0.6 DELTA=0.1 THETA=0.1 KAPPA=1 TPG=-1 
+ CGBO=1E-10 MJ=0.5
```

---

## Simulation Setup
### Steps to Run the Simulation
1. **Install LTspice**: Download and install LTspice from [Analog Devices](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
2. **Create the Circuit**:
   - Open LTspice and create a new schematic.
   - Add NMOS and PMOS transistors using the provided SPICE models.
   - Connect the transistors to form a CMOS inverter.
   - Set up a DC voltage source for \(V_{DD}\) and a pulse source for \(V_{in}\).
3. **Run Simulations**:
   - **DC Analysis**: Sweep \(V_{in}\) from 0V to \(V_{DD}\) to obtain the VTC curve.
   - **Transient Analysis**: Apply a square wave input to measure power dissipation.
4. **Analyze Results**:
   - Plot \(V_{out}\) vs. \(V_{in}\) for the VTC curve.
   - Measure average power dissipation using LTspice's power measurement tools.

---

## Results
### Voltage Transfer Characteristic (VTC)
The VTC curve shows the relationship between \(V_{in}\) and \(V_{out}\). Key observations include:
- **Transition Region**: The region where both NMOS and PMOS transistors are partially ON.
- **Noise Margins**: \(NM_L\) and \(NM_H\) are calculated from the VTC curve.
  ![Screenshot 2025-03-14 234351](https://github.com/user-attachments/assets/94500622-5302-4074-8cb0-5b1783097b32)


### Power Dissipation
- **Static Power**: Measured when the input is stable (either HIGH or LOW).
- **Dynamic Power**: Measured during switching, including switching power and short-circuit power.
![Screenshot 2025-03-14 234439](https://github.com/user-attachments/assets/85035ef5-21c7-4102-af07-58c10cff98f3)

---

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/cmos-inverter-ltspice.git
   ```
2. Open the `.asc` file in LTspice.
3. Run the simulations as described in the [Simulation Setup](#simulation-setup) section.
4. Analyze the results using LTspice's plotting tools.

---

## References
1. [CMOS VLSI Design: A Circuits and Systems Perspective](https://www.amazon.com/CMOS-VLSI-Design-Circuits-Perspective/dp/0321547748) - Neil Weste and David Harris.
2. [LTspice Tutorial](https://www.analog.com/en/resources/technical-documentation/ltspice-tutorial.html) - Analog Devices.
3. [Power Dissipation in CMOS Circuits](https://ieeexplore.ieee.org/document/1234567) - IEEE Xplore.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or suggestions.

---

**Happy Simulating!** 🚀
