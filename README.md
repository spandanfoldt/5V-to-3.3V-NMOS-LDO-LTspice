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

## Circuit Schematic
