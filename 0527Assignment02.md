
# Assignment: 1
<img width="395" height="82" alt="1Assignment" src="https://github.com/user-attachments/assets/0f31e081-7f61-4c3d-8aea-82b113283ba3" />

## Problem

Use the **Laplace transform** to solve the following second-order differential equation:

$$\frac{d^2x}{dt^2} - 3\frac{dx}{dt} + 2x = \delta(t)$$

With the initial conditions:
* $x(0) = 0$
* $x'(0) = 0$

---

### Step 1: Laplace
Apply the Laplace transform to both sides:

$$\left(s^2X(s) - sx(0) - x'(0)\right) - 3\left(sX(s) - x(0)\right) + 2X(s) = 1$$

**Note:** s is s-domain.


---

### Step 2:
Substitute $x(0) = 0$ and $x'(0) = 0$:

$$s^2X(s) - 3sX(s) + 2X(s) = 1$$

---

### Step 3: $X(s)$ 
Factor out $X(s)$ and solve:

$$(s^2 - 3s + 2)X(s) = 1 \implies X(s) = \frac{1}{(s - 1)(s - 2)}$$

---

### Step 4:
Expand using **Partial Fraction Decomposition**:

$$X(s) = \frac{1}{s - 2} - \frac{1}{s - 1}$$

**Note:** $$s1 = 2(\frac{1}{s - 2}), s2 = 1(\frac{1}{s - 1}$$), these two numbers will be used in the next step.()

---

### Step 5:
Convert back to the time domain using the standard transform table:

$$x(t) = e^{2t} - e^t$$

**Note:** t is time domain. Apply S1 and S2 together with e and the exponent t.

---

## Final System Response

$$x(t) = e^{2t} - e^t \quad (t \ge 0)$$

# Assignment: 6
<img width="430" height="95" alt="6Assignment" src="https://github.com/user-attachments/assets/98b3afec-9005-4640-9347-fd791c9298dc" />

## Problem

Find the **Fourier Transform** of the function:

$$f(t) = t e^{-5t} u(t)$$

---

## Solving Process

### Step 1: Base Transform Pair
From the standard Fourier Transform table, the transform of a basic decaying exponential is:

$$\mathcal{F}\{e^{-at} u(t)\} = \frac{1}{a + j\omega}$$

Setting $a = 5$:

$$\mathcal{F}\{e^{-5t} u(t)\} = \frac{1}{5 + j\omega}$$

---

### Step 2: Frequency Differentiation Property
Using the Fourier Transform:

$$\mathcal{F}\{t \cdot f(t)\} = j \frac{d}{d\omega} F(\omega)$$

Applying this to our base equation:

$$\mathcal{F}\{t e^{-5t} u(t)\} = j \frac{d}{d\omega} \left[ (5 + j\omega)^{-1} \right]$$

---

### Step 3: Compute the Derivative
Take the derivative with respect to $\omega$ using the chain rule:

$$\frac{d}{d\omega} \left[ (5 + j\omega)^{-1} \right] = -1 \cdot (5 + j\omega)^{-2} \cdot \frac{d}{d\omega}(5 + j\omega)$$

$$\frac{d}{d\omega} \left[ (5 + j\omega)^{-1} \right] = \frac{-j}{(5 + j\omega)^2}$$

---

### Step 4: Final Simplification
Multiply the derivative result by the front $j$:

$$F(\omega) = j \cdot \left[ \frac{-j}{(5 + j\omega)^2} \right]$$

Since $j \cdot (-j) = -j^2 = 1$:

$$F(\omega) = \frac{1}{(5 + j\omega)^2}$$

---

## Final Answer

$$F(\omega) = \frac{1}{(5 + j\omega)^2}$$
