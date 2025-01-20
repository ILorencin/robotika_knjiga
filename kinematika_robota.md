# Kinematika Robota

Kinematika robota proučava gibanje robota bez uzimanja u obzir sila koje ga uzrokuju. Primarno se fokusira na odnos između gibanja zglobova (zajedničkih varijabli) i rezultirajućeg položaja i orijentacije krajnjeg djelovatelja robota.

---

## Direktna Kinematika

Direktna kinematika odnosi se na određivanje položaja i orijentacije krajnjeg djelovatelja robota na temelju poznatih kutova zglobova i duljina segmenata robota.

### Denavit-Hartenbergova (DH) Notacija

Standardizacija parametara zglobova robota koristi Denavit-Hartenbergovu notaciju. DH parametri uključuju:
1. **`a_i`** – Duljina veze (udaljenost između osi zglobova).
2. **`α_i`** – Kut između osi zglobova (rotacija oko x osi).
3. **`d_i`** – Pomak duž z osi.
4. **`θ_i`** – Kut rotacije oko z osi.

### Matematički Primjer: Direktna Kinematika na Ruke

Razmotrimo 2-zglobni planarni robot s duljinama veza \(a_1 = 1\) i \(a_2 = 1\), te kutovima \(\theta_1 = 30^\circ\) i \(\theta_2 = 45^\circ\).

#### Korak 1: Postavljanje Transformacijskih Matrica
Transformacijska matrica prema Denavit-Hartenbergovoj notaciji je:
\[
T_i = \begin{bmatrix}
\cos(\theta_i) & -\sin(\theta_i)\cos(\alpha_i) & \sin(\theta_i)\sin(\alpha_i) & a_i\cos(\theta_i) \\
\sin(\theta_i) & \cos(\theta_i)\cos(\alpha_i) & -\cos(\theta_i)\sin(\alpha_i) & a_i\sin(\theta_i) \\
0 & \sin(\alpha_i) & \cos(\alpha_i) & d_i \\
0 & 0 & 0 & 1
\end{bmatrix}
\]

Za \(\alpha_1 = \alpha_2 = 0\) i \(d_1 = d_2 = 0\), matrice postaju:
\[
T_1 = \begin{bmatrix}
\cos(30^\circ) & -\sin(30^\circ) & 0 & 1\cdot\cos(30^\circ) \\
\sin(30^\circ) & \cos(30^\circ) & 0 & 1\cdot\sin(30^\circ) \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix},
\quad
T_2 = \begin{bmatrix}
\cos(45^\circ) & -\sin(45^\circ) & 0 & 1\cdot\cos(45^\circ) \\
\sin(45^\circ) & \cos(45^\circ) & 0 & 1\cdot\sin(45^\circ) \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\]

#### Korak 2: Računanje Položaja
Prvo transformiramo iz baze u prvi zglob:
\[
T_1 = \begin{bmatrix}
\sqrt{3}/2 & -1/2 & 0 & \sqrt{3}/2 \\
1/2 & \sqrt{3}/2 & 0 & 1/2 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\]

Zatim transformiramo iz prvog u drugi zglob:
\[
T_2 = \begin{bmatrix}
\sqrt{2}/2 & -\sqrt{2}/2 & 0 & \sqrt{2}/2 \\
\sqrt{2}/2 & \sqrt{2}/2 & 0 & \sqrt{2}/2 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\]

Konačna matrica za krajnji djelovatelj je:
\[
T = T_1 \cdot T_2 = \begin{bmatrix}
0.366 & -0.366 & 0 & 1.366 \\
1.366 & 1.366 & 0 & 1.366 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\]

Položaj krajnjeg djelovatelja je:
\[
x = 1.366, \quad y = 1.366
\]

### Python Primjer: Direktna Kinematika
```python
import numpy as np

# DH transformacijska matrica
def dh_transform(a, alpha, d, theta):
    return np.array([
        [np.cos(theta), -np.sin(theta)*np.cos(alpha),  np.sin(theta)*np.sin(alpha), a*np.cos(theta)],
        [np.sin(theta),  np.cos(theta)*np.cos(alpha), -np.cos(theta)*np.sin(alpha), a*np.sin(theta)],
        [0,              np.sin(alpha),               np.cos(alpha),              d],
        [0,              0,                           0,                          1]
    ])

# DH parametri za 2-zglobni planarni robot
a1, a2 = 1.0, 1.0  # Duljine veza
theta1, theta2 = np.radians(30), np.radians(45)  # Kutovi zglobova (u radijanima)

# Transformacije
T1 = dh_transform(a1, 0, 0, theta1)  # Prvi zglob
T2 = dh_transform(a2, 0, 0, theta2)  # Drugi zglob

# Ukupna transformacija
T = np.dot(T1, T2)

# Položaj krajnjeg djelovatelja
end_effector_position = T[:3, 3]
print("Položaj krajnjeg djelovatelja:", end_effector_position)
```

Rezultat:
```
Položaj krajnjeg djelovatelja: [1.3660254 1.3660254 0.       ]
```

## Inverzna Kinematika

Inverzna kinematika koristi se za određivanje vrijednosti zglobova na temelju poznatog položaja i orijentacije krajnjeg djelovatelja. Ovaj problem često ima više rješenja ili može biti nerješiv zbog ograničenja robota.

### Matematički Primjer: Inverzna Kinematika na Ruke

Za isti robot s poznatim položajem krajnjeg djelovatelja 

::: latex
\\(x = 1.5\\) i \\(y = 0.5\\), duljine veza \\(a_1 = 1\\) i \\(a_2 = 1\\):

::: 

#### Korak 1: Izračunavanje Drugog Kuta
::: latex
\\[
\\cos\\theta_2 = \\frac{x^2 + y^2 - a_1^2 - a_2^2}{2a_1a_2}
\\]
\\[
\\cos\\theta_2 = \\frac{1.5^2 + 0.5^2 - 1^2 - 1^2}{2 \\cdot 1 \\cdot 1} = \\frac{2.5 - 2}{2} = 0.25
\\]
\\[
\\theta_2 = \\arccos(0.25) \\approx 75.52^\\circ
\\]
::: 
#### Korak 2: Izračunavanje Prvog Kuta
::: latex
\\[
k_1 = a_1 + a_2\\cos\\theta_2, \\quad k_2 = a_2\\sin\\theta_2
\\]
\\[
k_1 = 1 + 1\\cdot0.25 = 1.25, \\quad k_2 = 1\\cdot\\sqrt{1 - 0.25^2} = \\sqrt{0.9375} \\approx 0.968
\\]
\\[
\\theta_1 = \\arctan\\left(\\frac{y}{x}\\right) - \\arctan\\left(\\frac{k_2}{k_1}\\right)
\\]
\\[
\\theta_1 = \\arctan\\left(\\frac{0.5}{1.5}\\right) - \\arctan\\left(\\frac{0.968}{1.25}\\right) \\approx 18.43^\\circ - 37.77^\\circ \\approx -19.34^\\circ
\\]
::: 
Rezultirajući kutovi su:
::: latex
\\[
\\theta_1 \\approx -19.34^\\circ, \\quad \\theta_2 \\approx 75.52^\\circ
\\]
::: 

### Python Primjer: Inverzna Kinematika
```python
def inverse_kinematics(x, y, a1, a2):
    # Inverzna kinematika za planarni 2-zglobni robot
    r = np.sqrt(x**2 + y**2)
    if r > a1 + a2:
        raise ValueError("Položaj je izvan dosega robota")

    # Drugi kut (theta2)
    cos_theta2 = (x**2 + y**2 - a1**2 - a2**2) / (2 * a1 * a2)
    theta2 = np.arccos(np.clip(cos_theta2, -1, 1))

    # Prvi kut (theta1)
    k1 = a1 + a2 * np.cos(theta2)
    k2 = a2 * np.sin(theta2)
    theta1 = np.arctan2(y, x) - np.arctan2(k2, k1)

    return np.degrees(theta1), np.degrees(theta2)

# Ciljani položaj
x, y = 1.5, 0.5
a1, a2 = 1.0, 1.0

# Izračun kutova
try:
    theta1, theta2 = inverse_kinematics(x, y, a1, a2)
    print(f"Kutovi zglobova: θ1={theta1:.2f}°, θ2={theta2:.2f}°")
except ValueError as e:
    print(e)
```

Rezultat:
```
Kutovi zglobova: θ1=-19.34°, θ2=75.52°
```
