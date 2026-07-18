# ⚡ 400W Class-D Audio Amplifier PCB

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![PCB Design](https://img.shields.io/badge/PCB-KiCad-blue.svg)
![Controller](https://img.shields.io/badge/Controller-IRS2092S-orange.svg)
![Project Status](https://img.shields.io/badge/Status-Design%20Completed-success.svg)

A custom-designed **400W Class-D Audio Amplifier PCB** developed using **KiCad**.  
This project is based on the **IRS2092S Class-D audio amplifier controller**, featuring a **±55V dual-rail power supply**, discrete MOSFET output stage, transistor-assisted gate-driving circuitry, feedback and compensation networks, bootstrap circuitry, and an LC output filter for efficient high-power audio amplification.

The project demonstrates the complete PCB design workflow in KiCad, including schematic development, component selection, footprint assignment, PCB layout, high-current routing, silkscreen labeling, 3D visualization, and preparation for fabrication.

---

## 📌 Project Overview

The **400W Class-D Audio Amplifier PCB** is a high-power audio electronics project designed around the **IRS2092S Class-D amplifier controller**.

The circuit receives an analog audio input and processes it through the IRS2092S controller. The controller generates high-frequency switching signals that drive the power MOSFET output stage.

The MOSFET half-bridge produces a high-power PWM waveform representing the original audio signal. This switching waveform is then passed through an **LC low-pass output filter**, which removes the high-frequency switching components and delivers the reconstructed amplified audio signal to the speaker.

The PCB has been designed with particular attention to high-current paths, MOSFET gate-drive routing, power distribution, grounding, output filtering, component placement, and thermal management.

> ⚠️ **Note:** The 400W rating represents the intended design target. Actual continuous RMS output power must be confirmed through physical prototype testing and measurement.

---

## ✨ Key Features

- IRS2092S-based Class-D amplifier design
- Approximately 400W target output capability
- ±55V dual-rail DC power supply
- Discrete power MOSFET half-bridge output stage
- Transistor-assisted MOSFET gate-drive circuitry
- Bootstrap high-side gate-drive circuit
- Analog audio input stage
- Feedback and compensation network
- LC low-pass speaker output filter
- Dedicated audio input connector
- Dedicated ±55V power connector
- Dedicated speaker output connector
- High-current PCB routing
- Mixed SMD and through-hole component design
- External heatsink compatibility for power MOSFETs
- Compact custom PCB layout
- Mechanical mounting holes
- Complete KiCad schematic and PCB design
- 3D PCB visualization
- Fabrication-ready PCB structure

---

## 🧠 System Architecture

```txt
Audio Input
      ↓
Input Coupling / Signal Conditioning
      ↓
IRS2092S Class-D Controller
      ↓
PWM / Gate Control Signals
      ↓
Gate Driver Stage
      ↓
Power MOSFET Half-Bridge
      ↓
LC Low-Pass Output Filter
      ↓
Speaker Output
```

---

## ⚙️ Hardware Description

The amplifier PCB is divided into several functional sections:

1. **Audio Input Section**
2. **IRS2092S Controller Section**
3. **Feedback and Compensation Section**
4. **Gate Driver Section**
5. **MOSFET Power Output Stage**
6. **Bootstrap Circuit**
7. **LC Output Filter Section**
8. **Power Supply and Decoupling Section**
9. **Speaker Output Section**

The incoming analog audio signal is fed into the IRS2092S controller through the input coupling and signal-conditioning circuitry.

The IRS2092S generates the required switching signals for the high-side and low-side MOSFETs.

The gate-driving stage improves MOSFET switching performance by providing suitable gate charge and discharge current.

The MOSFET half-bridge then produces a high-frequency PWM output. The LC low-pass filter removes the switching-frequency components and reconstructs the amplified audio waveform before sending it to the speaker.

---

## 🧩 Main Components

| Component | Description |
|---|---|
| IRS2092S | Main Class-D audio amplifier controller |
| Power MOSFETs | High-current half-bridge switching devices |
| 2N3904 | NPN transistor used in gate-drive/support circuitry |
| 2N3906 | PNP transistor used in gate-drive/support circuitry |
| TIP41A | Power transistor used in supporting circuitry |
| Output Inductor | Main inductor of the LC output filter |
| Filter Capacitor | Works with the output inductor to remove PWM switching components |
| Fast Diodes | Used for bootstrap and protection-related functions |
| Electrolytic Capacitors | Power filtering and local energy storage |
| Ceramic / Film Capacitors | High-frequency filtering, decoupling, and compensation |
| Resistors | Biasing, feedback, compensation, and gate control |
| Audio Input Connector | Provides analog audio input |
| Power Terminal | Provides +55V, GND, and -55V supply connections |
| Speaker Terminal | Provides amplified audio output |
| PCB | Custom-designed printed circuit board developed using KiCad |

---

## 🎛️ IRS2092S Controller Section

The amplifier is designed around the **IRS2092S**, a high-performance Class-D audio amplifier controller.

The controller performs several important functions, including:

- PWM generation
- High-side MOSFET control
- Low-side MOSFET control
- Gate-driver management
- Dead-time control
- Feedback processing
- Error amplification
- Oscillation control
- Shutdown functionality
- Bootstrap operation
- Over-current protection support

The IRS2092S acts as the central control component of the amplifier.

---

## 🎚️ Audio Input Section

The audio input section receives the low-level analog audio signal.

The input circuitry provides:

- DC blocking
- Signal coupling
- Input impedance control
- Signal conditioning
- Noise filtering
- Proper signal biasing

### Audio Input Connection

```txt
IN+  → Audio Signal
GND  → Audio Ground
```

A shielded audio cable is recommended to minimize unwanted noise and interference.

---

## ⚡ Power Supply

The amplifier is designed to operate using a symmetrical dual-rail DC power supply.

```txt
+55V
 GND
-55V
```

### Power Input Connection

```txt
+55V → Positive Supply Rail
GND  → Power Ground
-55V → Negative Supply Rail
```

The power supply must provide sufficient current for the intended output power and speaker impedance.

Important power supply considerations include:

- Sufficient current capacity
- Low output ripple
- Large bulk filtering capacitors
- Proper grounding
- Suitable rail fuses
- Correct polarity
- Soft-start or inrush limiting for high-power supplies

> ⚠️ Always verify the supply polarity before powering the PCB.

> ⚠️ ±55V DC is potentially dangerous and can cause electric shock, component failure, fire, or serious damage if handled incorrectly.

---

## 🔥 MOSFET Power Stage

The amplifier uses a discrete MOSFET half-bridge power output stage.

The MOSFET stage performs the high-power switching required for Class-D amplification.

Its main functions include:

- High-frequency switching
- PWM power amplification
- High-current output delivery
- Driving the LC output filter
- Transferring amplified power to the loudspeaker

Important MOSFET characteristics include:

- Drain-source voltage rating
- Drain current rating
- Low RDS(on)
- Gate charge
- Switching speed
- Thermal resistance
- Safe Operating Area

Proper MOSFET cooling is essential for reliable high-power operation.

---

## 🚀 Gate Driver Section

The amplifier includes transistor-assisted gate-driving circuitry between the IRS2092S and the MOSFET output stage.

The gate-driver section helps provide:

- Faster MOSFET switching
- Improved gate charge current
- Faster gate discharge
- Reduced switching losses
- Better MOSFET transition control
- Improved efficiency

Gate resistors are used to control the switching speed and reduce excessive ringing.

---

## ⚙️ Bootstrap Circuit

The high-side MOSFET requires a gate-drive voltage above the switching-node voltage.

A bootstrap circuit is therefore used to provide the required high-side gate-driving voltage.

The bootstrap section typically includes:

- Bootstrap diode
- Bootstrap capacitor
- Associated supply components

### Basic Operation

```txt
Low-Side MOSFET Turns ON
        ↓
Bootstrap Capacitor Charges
        ↓
High-Side Driver Activates
        ↓
High-Side Gate Voltage is Generated
        ↓
High-Side MOSFET Turns ON
```

Correct bootstrap component selection is important for reliable amplifier operation.

---

## 🔄 Feedback and Compensation Section

The amplifier includes a feedback and compensation network connected to the IRS2092S controller.

This section helps provide:

- Stable closed-loop gain
- Improved linearity
- Reduced distortion
- Stable frequency response
- Better output accuracy
- Improved control-loop stability

The feedback routing should be kept away from noisy high-current and high-frequency switching areas wherever possible.

---

## 🌀 LC Output Filter

Class-D amplifiers generate a high-frequency PWM waveform at the MOSFET output stage.

An **LC low-pass filter** is used to remove the switching-frequency components and recover the amplified audio waveform.

### Signal Path

```txt
MOSFET Half-Bridge
        ↓
Switching Node
        ↓
Output Inductor
        ↓
Filter Capacitor
        ↓
Speaker Output
```

The LC output filter helps:

- Remove PWM switching components
- Reduce high-frequency noise
- Reduce EMI
- Recover the audio-frequency waveform
- Prevent excessive switching energy from reaching the speaker

The output inductor must be capable of carrying high current without magnetic saturation.

---

## 🔊 Speaker Output

The amplified and filtered audio signal is provided through the speaker output terminal.

```txt
SPK+ → Amplified Audio Signal
GND  → Speaker Return
```

Typical speaker loads may include:

```txt
4Ω Speaker
8Ω Speaker
```

The safe speaker impedance depends on the MOSFET ratings, power supply capability, thermal performance, and overall circuit design.

---

## 🔢 Output Power Calculation

The approximate amplifier output power can be calculated using:

```txt
P = Vrms² / R
```

Where:

```txt
P     = Output Power in Watts
Vrms  = RMS Output Voltage
R     = Speaker Load Resistance
```

Example:

```txt
Vrms = 40V
R = 4Ω

P = 40² / 4

P = 1600 / 4

P = 400W
```

Therefore:

```txt
40 Vrms into 4Ω ≈ 400W
```

Actual output capability depends on:

- Supply voltage under load
- Speaker impedance
- MOSFET conduction losses
- MOSFET switching losses
- Output filter losses
- PCB resistance
- Power supply current capability
- Cooling
- Distortion limit
- Thermal conditions

---

## 🌡️ Thermal Management

The power MOSFETs require adequate thermal management.

A suitable external heatsink should be installed.

### Typical Thermal Arrangement

```txt
Power MOSFET
      ↓
Thermal Compound
      ↓
Thermal Pad / Electrical Insulator
      ↓
Aluminium Heatsink
      ↓
Natural or Forced Airflow
```

Recommended cooling methods include:

- Large aluminium heatsink
- High-quality thermal compound
- Electrically insulating thermal pads where required
- Proper MOSFET mounting
- Good enclosure ventilation
- Forced-air cooling for prolonged high-power operation

A cooling fan is recommended when operating the amplifier continuously at high output levels.

---

## 🖥️ PCB Design

The PCB was designed using **KiCad** and includes:

- Schematic capture
- Component selection
- Footprint assignment
- PCB layout
- Component placement
- Manual routing
- High-current trace routing
- Power distribution
- Ground routing
- Signal routing
- Silkscreen labeling
- Mounting holes
- 3D PCB visualization
- Fabrication preparation

The board was organized to keep sensitive audio/control circuitry separated from the high-current switching section as much as practical.

---

## ⚡ High-Current PCB Routing

Important high-current paths include:

```txt
Power Supply
     ↓
Power MOSFET Stage
     ↓
Output Inductor
     ↓
Speaker Output
     ↓
Power Ground Return
```

High-current tracks should be:

- Short
- Wide
- Direct
- Low resistance
- Free from unnecessary vias

For higher current capability, thicker PCB copper such as **2 oz copper** can be considered.

---

## ⚡ Switching Node Considerations

The switching node between the MOSFET half-bridge and output inductor is one of the most critical sections of the PCB.

The switching-node copper area should be kept as small as practical.

A large switching node can increase:

- EMI
- Parasitic capacitance
- Ringing
- Noise coupling
- Switching losses

Recommended layout:

```txt
MOSFET Half-Bridge
        ↓
Short Switching Node
        ↓
Output Inductor
```

---

## 🔁 Gate Routing Considerations

The MOSFET gate-drive traces should be:

- Short
- Direct
- Low inductance
- Located away from noisy switching nodes

Recommended routing structure:

```txt
Gate Driver
     ↓
Gate Resistor
     ↓
MOSFET Gate
     ↓
Short Return Path
```

Poor gate routing may result in:

- Ringing
- False MOSFET turn-on
- Shoot-through
- EMI
- Excessive heating
- MOSFET failure

---

## 🌍 Grounding

Grounding is extremely important in Class-D amplifier PCB design.

The design should carefully manage:

```txt
Signal Ground
    ├── Audio Input
    ├── Feedback Circuit
    └── Controller Reference

Power Ground
    ├── MOSFET Current Return
    ├── Speaker Return
    └── Power Supply Return
```

High-current return paths should not flow through sensitive low-level audio ground paths.

---

## 🔋 Decoupling and Filtering

The circuit includes decoupling and filtering components to maintain stable power rails and reduce switching noise.

These include:

- Electrolytic bulk capacitors
- Ceramic bypass capacitors
- Film capacitors
- Bootstrap capacitor
- Local supply decoupling

High-frequency bypass capacitors should be placed close to the relevant switching and control devices.

---

## 🛡️ Recommended Protection Features

Future revisions of the amplifier can include additional protection features such as:

- Speaker DC protection relay
- Power-on speaker delay
- Over-temperature protection
- Over-current protection
- Short-circuit protection
- Supply rail fuses
- Undervoltage protection
- Overvoltage protection
- Soft-start circuitry
- Inrush-current limiting
- Clip indicator
- Fault indicator
- Automatic cooling fan control

---

## 🔊 Speaker Protection

A separate speaker protection circuit is recommended for practical high-power amplifier use.

### Suggested Architecture

```txt
Amplifier Output
      ↓
DC Fault Detection
      ↓
Power-On Delay
      ↓
Protection Relay
      ↓
Speaker
```

This can protect the speaker from:

- DC output faults
- Turn-on transients
- Turn-off transients
- Amplifier failure

---

## 📷 PCB Preview

The project includes schematic, PCB layout, and 3D visualization previews.

### Schematic

<img width="1562" height="762" alt="image" src="https://github.com/user-attachments/assets/9615b790-d169-4d05-937b-5317f0429879" />


![Schematic](images/schematic.png)

### PCB Layout

<img width="1599" height="751" alt="image" src="https://github.com/user-attachments/assets/d3766960-de85-4f77-ab17-6dc1ad065d25" />


![PCB Layout](images/pcb-layout.png)

### 3D View

<img width="1377" height="657" alt="image" src="https://github.com/user-attachments/assets/e3865f94-aa8d-4316-ba44-9c924d0cc726" />
<img width="1025" height="742" alt="image" src="https://github.com/user-attachments/assets/9af21246-14c5-46f6-8b5d-e2617bc589ed" />
<img width="1118" height="741" alt="image" src="https://github.com/user-attachments/assets/e4d3780a-b030-478a-9cd8-2bc2e52c33a1" />
<img width="1147" height="855" alt="image" src="https://github.com/user-attachments/assets/5d5a716a-16b8-49b2-834e-78b2ac2551a0" />
<img width="1286" height="616" alt="image" src="https://github.com/user-attachments/assets/8643bc95-d730-42e4-b0ba-aa882e2b4b71" />


![3D View](images/3d-front.png)

---

## 🧪 Recommended Testing

Before connecting a loudspeaker, the amplifier should be tested carefully.

Recommended testing sequence:

1. Perform a complete visual inspection.
2. Check for short circuits between the power rails.
3. Verify component orientation and polarity.
4. Apply power using a current-limited supply where possible.
5. Confirm all internal supply voltages.
6. Verify the IRS2092S operation.
7. Check high-side and low-side gate signals using an oscilloscope.
8. Verify correct dead time between MOSFET switching signals.
9. Inspect the switching node waveform.
10. Connect a suitable high-power dummy load.
11. Apply a low-level 1 kHz sine-wave input.
12. Gradually increase the signal level.
13. Monitor output voltage and waveform.
14. Measure MOSFET and output inductor temperatures.
15. Check for clipping and instability.
16. Connect a real speaker only after successful dummy-load testing.

> ⚠️ Appropriate differential or isolated probing techniques must be used when measuring high-side switching waveforms.

---

## 📊 Recommended Performance Measurements

| Measurement | Purpose |
|---|---|
| RMS Output Voltage | Calculate real output power |
| THD+N | Measure audio distortion |
| Frequency Response | Verify audio bandwidth |
| Signal-to-Noise Ratio | Evaluate noise performance |
| DC Offset | Verify speaker safety |
| Efficiency | Evaluate Class-D performance |
| MOSFET Temperature | Verify thermal design |
| Inductor Temperature | Verify output filter performance |
| Switching Frequency | Verify controller operation |
| EMI / EMC | Evaluate switching interference |

---

## 📈 Efficiency

Class-D amplifiers are designed to achieve high efficiency compared with conventional linear amplifier topologies.

Efficiency can be calculated using:

```txt
Efficiency (%) = (Output Power / Input Power) × 100
```

The actual efficiency depends on:

- MOSFET conduction losses
- MOSFET switching losses
- Gate-driver losses
- Output inductor losses
- PCB resistance
- Power supply losses
- Load impedance

---

## 🚀 Applications

This PCB can be used for:

- High-power audio amplifier development
- Class-D amplifier experimentation
- Power electronics learning
- Audio electronics research
- MOSFET switching studies
- Gate-driver circuit experimentation
- High-current PCB design practice
- KiCad PCB design portfolio development
- Audio hardware prototyping
- Educational electronics projects
- Custom speaker amplifier systems

---

## 🔮 Future Improvements

Possible future improvements include:

- Speaker protection relay
- DC fault detection
- Temperature sensing
- Automatic cooling fan controller
- Improved MOSFET gate-loop routing
- Reduced switching-node area
- Improved feedback routing
- Additional EMI filtering
- Optimized snubber network
- Clip indicator
- Fault indicator LEDs
- Soft-start circuitry
- Inrush-current limiting
- Balanced audio input
- Differential audio input
- Higher-current connectors
- Improved heatsink mounting
- Additional PCB test points

---

## ⚠️ Safety Notice

This project operates using relatively high DC voltage and potentially very high current.

Potential hazards include:

- Electric shock
- Severe burns
- Fire
- Exploding capacitors
- MOSFET failure
- Loudspeaker damage
- Power supply damage
- Test equipment damage

Large electrolytic capacitors may remain charged after power is removed.

Always:

- Disconnect the power before touching the PCB
- Verify that capacitors are fully discharged
- Use appropriate fuses
- Use current limiting during first power-up
- Use insulated tools
- Verify power polarity
- Use correct oscilloscope probing techniques
- Do not connect expensive speakers during initial testing

This project should only be assembled and tested by individuals familiar with high-power electronics, Class-D amplifiers, PCB troubleshooting, and electrical laboratory safety.

---

## 👨‍💻 Author

**Fernando S.M.H.G.**

Designed using **KiCad**.

Project work includes:

- Schematic design
- Component selection
- Footprint assignment
- PCB placement
- High-current routing
- Signal routing
- Power routing
- Grounding design
- Silkscreen design
- 3D PCB visualization
- Mechanical PCB layout

---

## 📜 License

This project is licensed under the **MIT License**.

You are free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the project files, subject to the terms of the MIT License.

See the `LICENSE` file for complete details.

### MIT License

```txt
MIT License

Copyright (c) 2026 Fernando S.M.H.G.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this project and associated documentation files (the "Project"), to deal
in the Project without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Project, and to permit persons to whom the Project is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Project.

THE PROJECT IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE PROJECT OR THE USE OR OTHER DEALINGS IN
THE PROJECT.
```

---

## ⚠️ Disclaimer

This project is provided **"AS IS"** without warranty.

The author does not guarantee:

- 400W continuous RMS output
- Electrical safety
- Commercial suitability
- Regulatory compliance
- EMI / EMC compliance
- Specific audio performance
- Thermal performance
- Long-term reliability

Anyone building or modifying this design is responsible for verifying:

- Circuit correctness
- Component ratings
- MOSFET ratings
- PCB current capability
- Trace widths
- Electrical clearances
- Thermal performance
- Protection circuitry
- Power supply capability
- Electrical safety

The author is not responsible for personal injury, equipment damage, loudspeaker damage, fire, incorrect assembly, semiconductor failure, or other losses resulting from the construction or use of this project.

---

## ⭐ Support

If you find this project useful:

- ⭐ Star the repository
- 🍴 Fork the project
- 🔧 Suggest improvements
- 🐛 Report design issues
- 📢 Share the project with electronics enthusiasts

---

<p align="center">
  <b>⚡ 400W Class-D Audio Amplifier PCB ⚡</b>
</p>

<p align="center">
  IRS2092S-Based High-Power Audio Amplifier & Custom PCB Design
</p>

<p align="center">
  Designed with ❤️ using KiCad
</p>
