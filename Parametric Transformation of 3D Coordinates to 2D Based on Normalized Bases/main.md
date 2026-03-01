# Parametric Transformation of 3D Coordinates to 2D Based on Normalized Bases

**Author:** Robinson Stalin Cajas Molina  
**Date:** February 28, 2026

---

## Introduction

This study presents the derivation of a parametric transformation that maps three-dimensional coordinates onto a two-dimensional plane. The construction is based on a normalized vector basis defined from the geometric dimensions of a canvas of size **n × m**, allowing width, height, and depth to be represented algebraically within a projected system.

---

## Vector Basis Definition

From the reference point

$$
P_0 = \left(\frac{n}{2}, -\frac{m}{2}\right)
$$

we define the directional vectors of the system:

$$
V_1 = \left(0,\frac{m}{2}\right), \quad
V_2 = \left(\frac{n}{2},-\frac{m}{2}\right), \quad
V_3 = \left(-\frac{n}{2},-\frac{m}{2}\right)
$$

These vectors form an oblique basis on the representation plane.

---

## Basis Normalization

We compute the Euclidean magnitudes of the diagonal vectors:

$$|V_2| = |V_3| = \sqrt{\left(\frac{n}{2}\right)^2 + \left(-\frac{m}{2}\right)^2} = \frac{\sqrt{n^2 + m^2}}{2}$$

Defining the scale constant

$$
k = \frac{n}{\sqrt{n^2+m^2}},
$$

we obtain the unit vectors:

$$
U_{V_1}=(0,1), \quad
U_{V_2}=\left(k, -k \frac{m}{n}\right), \quad
U_{V_3}=\left(-k, -k \frac{m}{n}\right)
$$

This normalization preserves directional scale consistency in the transformation.

---

## Parametric Transformation Model

Let a 3D point be parameterized as

$$
P_{3D}=(c,a,b).
$$

Its planar representation is obtained through linear combination over the normalized basis:

$$
P_{2D} =
\binom{n/2}{-m/2 + a}
+
b \binom{k}{-k \frac{m}{n}}
+
c \binom{-k}{-k \frac{m}{n}}.
$$

Separating components:

**Horizontal component**

$$
X = \frac{n}{2} + k(b - c)
$$

**Vertical component**

$$
Y = -\frac{m}{2} + a - k \frac{m}{n}(b + c)
$$

These equations define a parametric affine transformation from 3D coordinates to 2D.

---

## Numerical Verification

Evaluate the model for:

- n = 6  
- m = 6  
- P(1,1,1)

$$
X_{2D} = 3 + 0.707(1 - 1) = 3
$$

$$
Y_{2D} = -3 + 1 - 0.707(1 + 1) \approx -3.41
$$

The result confirms algebraic consistency.

---

## Computational Implementation

For practical use, adopt the mapping:

$$
c \rightarrow x,\qquad
a \rightarrow y,\qquad
b \rightarrow z
$$

---

## Final Projection Equations

$$
X_{2D} = \frac{n}{2} + \left( \frac{n}{\sqrt{n^2+m^2}} \right) (z - x)
$$

$$
Y_{2D} = -\frac{m}{2} + y - \left( \frac{m}{\sqrt{n^2+m^2}} \right) (z + x)
$$
