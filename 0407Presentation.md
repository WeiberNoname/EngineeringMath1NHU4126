# 題目一、電機工程案例：RC 充電電路 工程問題：電容在接上直流電源後，電壓如何隨時間變化？
## First-Order Differential Equations in Electrical Engineering
---

### 1. Problem Statement
電容在接上直流電源後，電壓如何隨時間變化？

### 2. Mathematical Modeling
$$RC \frac{dV}{dt} + V = E$$

Where:
* $V$: Capacitor voltage (V)
* $E$: Source voltage (V)
* $R$: Resistance ($\Omega$)
* $C$: Capacitance (F)

---

### 3. Derivation (Separation of Variables)

#### Step 1: Isolate the Derivative
$$RC \frac{dV}{dt} = E - V$$
$$\frac{dV}{dt} = \frac{E - V}{RC}$$

#### Step 2: Separate and Integrate
$$\int \frac{1}{E - V} dV = \int \frac{1}{RC} dt$$

#### Step 3: Use $u$-substitution
1. left. let $u = E - V$. Then, $du = -dV$. 

2. Integrate directly with respect to $t$, treating $RC$ as a constant.

$$-\ln|E - V| = \frac{t}{RC} + K$$

> **Note on Rigor:** We use the absolute value $|E - V|$ because the natural log is only defined for positive values. In this physical system, $E \ge V$, so $E - V$ remains positive.

#### Step 4: Solve for $V(t)$
Multiply by $-1$ and exponentiate:
$$E - V = e^{-\frac{t}{RC} - K}$$

$$E - V = A e^{-t/RC} \quad (\text{where } A = \pm e^{-K} \text{, and } e^{-\frac{t}{RC}} * e^{-K} = E - V)$$

$$V(t) = E - A e^{-t/RC}$$

#### Step 5: Apply Initial Conditions
Assuming the capacitor is uncharged() at $t = 0$ ($V(0) = 0$):
$$0 = E - A e^0 \implies A = E$$

---

### 4. Final Solution
The voltage across the capacitor as a function of time is:
$$V(t) = E(1 - e^{-t/RC})$$ 

(due to: $$V(t) = E - E e^{-t/RC}$$, where A = E from step 5)

### 5. 工程意義 (Engineering Significance)

一階 RC 電路最核心的物理行為摘要：

#### 核心指標
* **時間常數 ($\tau = RC$)**：系統反應速度的基準。
  * 當 $t = 1\tau$ 時，電容電壓達到 **63.2%**。
* **穩態 (Steady State)**：當 $t \ge 5\tau$ 時。
  * 電容電壓 $V(t) \approx E$，此時電容視為**斷路 (Open Circuit)**。

#### 充電進度表 (Charging Progress)
| 時間 (Time) | 電壓比例 (% of $E$) | 狀態 (Status) |
| :--- | :--- | :--- |
| $1\tau$ | **63.2%** | 快速上升期 (Fast Rise) |
| $3\tau$ | **95.0%** | 接近飽和 (Near Full) |
| $5\tau$ | **99.3%** | 進入穩態 (Steady State) |



#### 實際應用 (Quick Applications)
1. **定時器 (Timers)**：利用充電時間來延遲訊號。
2. **濾波器 (Filters)**：消除高頻雜訊。
3. **去彈跳 (Debouncing)**：讓機械開關訊號變平滑。
