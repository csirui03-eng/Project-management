# Cramer's rule

**The rule.** For any square system with nonzero determinant, unknown number $n$ equals the system determinant with column $n$ swapped out for the drive vector, divided by the untouched system determinant.

**The 2 by 2 written out:**

$$\begin{bmatrix} a & b \\[2pt] c & d \end{bmatrix}\begin{bmatrix} x_1 \\[2pt] x_2 \end{bmatrix} = \begin{bmatrix} f_1 \\[2pt] f_2 \end{bmatrix}$$

$$x_1 = \frac{\begin{vmatrix} f_1 & b \\[2pt] f_2 & d \end{vmatrix}}{\begin{vmatrix} a & b \\[2pt] c & d \end{vmatrix}} \qquad\qquad x_2 = \frac{\begin{vmatrix} a & f_1 \\[2pt] c & f_2 \end{vmatrix}}{\begin{vmatrix} a & b \\[2pt] c & d \end{vmatrix}}$$

**When to reach for it:**

- One unknown wanted, not all of them.
- Symbolic work, not numeric.
- The determinant wanted on display as its own object.

Numerically it is the expensive route, a full determinant per unknown, so solvers eliminate under the hood instead.
