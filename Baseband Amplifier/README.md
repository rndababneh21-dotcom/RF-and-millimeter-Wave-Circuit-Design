# Single-Ended Common-Source Baseband Amplifier

Design, theoretical analysis, **Qucs-s** simulation, and hardware implementation of a single-ended Common-Source (CS) NMOS baseband amplifier using the **CD4007** transistor array (Integrated Circuits Group, Eindhoven University of Technology).

## Key Specifications & Performance

| Parameter | Target / Simulated Value |
| :--- | :--- |
| **Topology** | Single-Ended Common-Source with Voltage-Divider Biasing |
| **Active Device** | CD4007 / CD4007UB NMOS Transistor |
| **Supply Voltage ($V_{DD}$)** | $5\text{ V}$ |
| **Operating Frequency Range** | $10\text{ Hz} - 100\text{ kHz}$ (up to $1\text{ MHz}$) |
| **Voltage Gain ($A_v$)** | $7\text{ V/V}$ ($\approx 16.9\text{ dB}$) |
| **Current Gain ($A_i$)** | $19.83\text{ A/A}$ |
| **Power Gain ($A_p$)** | $\approx 21.4\text{ dB}$ |
| **Input / Output Impedance** | $Z_{in} = 121.8\text{ k}\Omega$ / $R_{out} = 41.2\text{ k}\Omega$ |
| **Max Linear Input Swing** | $0.16\text{ V}$ ($P_{1dB} = 184.2\text{ mV}$) |

## Project Structure & Simulation Files

* **`Amplifier_Design.pdf`**: Complete engineering report covering DC/AC calculations, small-signal & high-frequency Miller modeling, Qucs-s simulations, and hardware measurements.
* **Qucs-s Schematics (`Ngspice`)**:
  * `Amplifier_CS.R.sch` – Transient input/output waveforms ($V_{in}(t)$, $V_{out}(t)$)
  * `Amplifier_CS.R2.sch` – `R4.sch` – Voltage, current, and power gain analyses
  * `Amplifier_CS.R5.sch` – `R6.sch` – Input and output impedance characterization
  * `Amplifier_CS.R7.sch` – Linearity and 1-dB compression point ($P_{1dB}$)
  * `Amplifier_CS.R8.sch` – `R10.sch` – Time-domain current and power profiles

## Hardware Implementation
The physical prototype was built on a breadboard using the **CD4007UB** IC, driven by an **Arduino Uno** PWM timer through an RC low-pass filter ($R = 47\text{ k}\Omega$, $C = 10\ \mu\text{F}$), with automated DC transfer and gain measurements acquired via **GNU Octave**.
