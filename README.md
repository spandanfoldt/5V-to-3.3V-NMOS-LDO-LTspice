# 5V to 3.3V NMOS Source-Follower LDO Regulator

A discrete Low-Dropout Regulator (LDO) designed and simulated in LTspice to down-convert a **5.0V** supply ($V_{bat}$) to a regulated **3.3V** output ($V_{out}$) delivering up to **100mA** load current. 

The topology utilizes a **2N7002 NMOS** pass element configured as a source-follower, regulated via an **OP07 operational amplifier** in a negative feedback loop with a **1.2V** voltage reference ($V_{ref}$).

---

## Technical Specifications

| Parameter | Symbol | Value | Unit |
| :--- | :--- | :--- | :--- |
| **Input Rail Voltage** | $V_{bat}$ | 5.0 | V |
| **Regulated Output Voltage** | $V_{out}$ | 3.3 | V |
| **Reference Voltage** | $V_{ref}$ | 1.2 | V |
| **Nominal Load Resistance** | $R_{load}$ | 33 | $\Omega$ |
| **Nominal Load Current** | $I_{load}$ | 100 | mA |
| **Op-Amp Bias Rails** | $V_{bias\pm}$ | $\pm 8.0$ | V |
| **Gate Drive Voltage** | $V_g$ | ~5.93 | V |

---

## Theoretical Calculations vs. Simulation Results

All circuit operating parameters were derived theoretically by hand and subsequently verified against LTspice simulation waveforms.

### Design Equations & Derivations

1. **Output Voltage ($V_{out}$):**
   $$V_{out} = V_{ref} \times \left(1 + \frac{R_{fb1}}{R_{fb2}}\right) = 1.2\text{V} \times \left(1 + \frac{21\text{k}\Omega}{12\text{k}\Omega}\right) = 1.2\text{V} \times 2.75 = \mathbf{3.30\text{V}}$$

2. **Feedback Node Voltage ($V_{fb}$):**
   $$V_{fb} = V_{out} \times \left(\frac{R_{fb2}}{R_{fb1} + R_{fb2}}\right) = 3.30\text{V} \times \left(\frac{12\text{k}\Omega}{33\text{k}\Omega}\right) = \mathbf{1.20\text{V}}$$

3. **Load Current ($I_{load}$):**
   $$I_{load} = \frac{V_{out}}{R_{load}} = \frac{3.30\text{V}}{33\Omega} = \mathbf{100\text{mA}}$$

4. **Pass Transistor Power Dissipation ($P_{M1}$):**
   $$V_{DS} = V_{bat} - V_{out} = 5.0\text{V} - 3.30\text{V} = 1.70\text{V}$$
   $$P_{M1} = V_{DS} \times I_{load} = 1.70\text{V} \times 100\text{mA} = \mathbf{170\text{mW}}$$

5. **Gate Drive Requirement ($V_g$):**
   $$V_g = V_{out} + V_{GS} = 3.30\text{V} + 2.63\text{V} = \mathbf{5.93\text{V}}$$
   *(Where $V_{GS} \approx 2.63\text{V}$ is the gate-to-source threshold voltage required for 100mA current flow).*

---

### Verification Summary Table

| Parameter | Hand Calculated | LTspice Simulation | Result / Status |
| :--- | :--- | :--- | :--- |
| **$V_{out}$** | 3.30 V | 3.30 V | Verified |
| **$V_{fb}$** | 1.20 V | 1.20 V | Verified |
| **$I_{load}$** | 100 mA | 100 mA | Verified |
| **$P_{NMOS}$** | 170 mW | 170 mW | Verified |
| **$V_g$** | 5.93 V | 5.93 V | Verified |

# 5V to 3.3V Discrete NMOS LDO Regulator

A discrete Low-Dropout Regulator (LDO) designed in LTspice to regulate a **5V** input down to **3.3V** at **100mA** using an NMOS source-follower and OP07 feedback loop.

---

## Design Calculations vs. Waveform Verification

The operating parameters were calculated by hand and subsequently verified against the LTspice transient simulation waveforms.

### Hand Calculations

* **Output Voltage ($V_{out}$):**
  $$V_{out} = V_{ref} \times \left(1 + \frac{R_{fb1}}{R_{fb2}}\right) = 1.2\text{V} \times \left(1 + \frac{21\text{k}\Omega}{12\text{k}\Omega}\right) = \mathbf{3.30\text{V}}$$

* **Feedback Voltage ($V_{fb}$):**
  $$V_{fb} = V_{out} \times \left(\frac{R_{fb2}}{R_{fb1} + R_{fb2}}\right) = 3.30\text{V} \times \left(\frac{12\text{k}\Omega}{33\text{k}\Omega}\right) = \mathbf{1.20\text{V}}$$

* **Load Current ($I_{load}$):**
  $$I_{load} = \frac{V_{out}}{R_{load}} = \frac{3.30\text{V}}{33\Omega} = \mathbf{100\text{mA}}$$

* **Transistor Power Dissipation ($P_{M1}$):**
  $$P_{M1} = (V_{bat} - V_{out}) \times I_{load} = (5.0\text{V} - 3.30\text{V}) \times 100\text{mA} = \mathbf{170\text{mW}}$$

* **Gate Drive Voltage ($V_g$):**
  $$V_g = V_{out} + V_{GS} = 3.30\text{V} + 2.63\text{V} = \mathbf{5.93\text{V}}$$

---

### Verification Summary

| Parameter | Hand Calculated | Waveform Verified | Status |
| :--- | :--- | :--- | :--- |
| **Output Voltage ($V_{out}$)** | 3.30 V | 3.30 V | Verified |
| **Feedback Voltage ($V_{fb}$)** | 1.20 V | 1.20 V | Verified |
| **Load Current ($I_{load}$)** | 100 mA | 100 mA | Verified |
| **Power Dissipation ($P_{M1}$)** | 170 mW | 170 mW | Verified |
| **Gate Voltage ($V_g$)** | 5.93 V | 5.93 V | Verified |

---

## Waveforms

![Simulation Waveforms](waveforms/ldo_performance_overview.png)
*Figure 1: LTspice waveform verification for $V_{out}$, $V_{fb}$, $I_{load}$, and $P_{M1}$.*
