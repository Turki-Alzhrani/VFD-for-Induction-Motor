# VFD-for-Indction-motor
analyze three-phase induction motor using a Variable Frequency Drive (VFD) and to measure and compare the starting current and torque characteristics of the motor with and without the VFD soft-start system.

Here is a concise, professional version of the README. It gets straight to the point while keeping all the technical details.

---

# VFD Soft-Starter for 5HP Induction Motor (MATLAB/Simulink)

## Project Summary
This project simulates a **Variable Frequency Drive (VFD)** system using **Open-Loop V/f Control** to soft-start a **5HP Three-Phase Induction Motor**. The simulation demonstrates how VFDs mitigate high inrush currents and mechanical stress compared to Direct-On-Line (DOL) starting.

## Key Features
* **Control Strategy:** Open-Loop V/f (Constant Flux) with SPWM modulation.
* **Soft-Start Mechanism:** Utilizes DC-Link capacitor charging dynamics for a natural voltage ramp.
* **Interactive Control:** Real-time speed adjustment via a dashboard knob.
* **Comparative Study:** Includes a baseline DOL simulation to quantify performance improvements.

## System Components
1.  **Power Circuit:**
    * **Source:** 3-Phase Programmable Source (adjusted to 615V L-L).
    * **Rectifier & Filter:** Diode bridge with an RC Low-Pass Filter (DC Link) to smooth ripples (~751V DC).
    * **Inverter:** 3-Phase IGBT bridge driven by SPWM.
2.  **Control Circuit:**
    * Generates SPWM pulses by comparing a reference sine wave with a high-frequency sawtooth carrier.
    * Includes a PI controller for stability.

## Results: VFD vs. DOL
The simulation compares the VFD soft-starter against a standard DOL start:

![DOL Circuit](DOL.png)
![VFD Circuit](VFD.png)

![DOL Result](SPEED%20VS%20CURRENT%20WITHOUT%20VFD.png)

### Direct-On-Line (DOL) Results

**Rotor Speed (Top Plot)**
The rotor speed rises very quickly with a noticeable abrupt jump at the beginning. The machine reaches its final speed almost instantly, which shows the aggressive acceleration typical of direct-on-line (DOL) starting. Small oscillations appear due to the sudden high torque applied at startup.

**Stator Current (Bottom Plot)**
The stator current shows a very large inrush spike at the moment of startup, reaching a high peak before settling into a steady waveform. This high current peak is characteristic of DOL starting and indicates strong electrical stress on the machine windings.

---

![VFD Result](SPEED%20VS%20CURRENT%20WITH%20VFD.png)

### VFD Soft-Starting Results

**Rotor Speed (Top Plot)**
The rotor speed increases smoothly and reaches its final value without any overshoot. The startup is gradual and controlled, showing that the updated VFD model provides a stable acceleration. The small oscillation at the beginning is part of the normal transient response.

**Stator Current (Bottom Plot)**
The stator current starts at a low and controlled level instead of showing a large inrush spike. This smooth behavior is a result of the VFD soft-start method, which gradually increases voltage and frequency. The current quickly settles into a steady waveform, confirming that the starting current has been successfully reduced.

## How to Run
1.  Open the `.slx` file in MATLAB/Simulink.
2.  Click **Run**.
3.  Use the **Dashboard Knob** to vary the motor speed.
4.  Check the **Scopes** to view Current, Speed, and Torque waveforms.


---
**Authors:** [Turki Alzahrani and Majed Gandaih and Abdullah Al-Ahmari , Osama Zawawi].
