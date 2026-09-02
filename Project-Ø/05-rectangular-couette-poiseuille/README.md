# 05 - Three-Dimensional Rectangular Couette-Poiseuille Flow

This COMSOL model describes steady, incompressible, fully developed flow through a finite rectangular channel. The flow is driven simultaneously by motion of the upper wall and by a constant streamwise pressure gradient.

## Geometry and coordinates

The channel axis is the $x$ direction:

$$
0<x<L,
\qquad
-\frac{w}{2}<y<\frac{w}{2},
\qquad
0<z<h.
$$

Here $L$ is the channel length, $w$ is its width, and $h$ is its height. The velocity is assumed to be fully developed and unidirectional:

$$
\mathbf{u}=u(y,z)\,\mathbf{e}_x.
$$

Consequently, the analytical velocity is independent of $x$. The pressure varies linearly along the channel.

## Assumptions

- Steady flow
- Incompressible Newtonian fluid
- Constant dynamic viscosity $\mu$
- Fully developed unidirectional velocity
- No body force in the $x$ direction
- Upper wall at $z=h$ moving with velocity $U\mathbf{e}_x$
- Bottom wall and both side walls stationary
- Constant pressure gradient along $x$

Define

$$
\Delta p=p_{\mathrm{in}}-p_{\mathrm{out}},
\qquad
G=\frac{\Delta p}{L}=-\frac{dp}{dx}.
$$

Thus $G>0$ drives flow in the positive $x$ direction, and

$$
p(x)=p_{\mathrm{in}}-Gx.
$$

## Governing equation

The $x$-momentum equation reduces to

$$
\mu\left(
\frac{\partial^2 u}{\partial y^2}
+\frac{\partial^2 u}{\partial z^2}
\right)
=\frac{dp}{dx}=-G,
$$

or

$$
\frac{\partial^2 u}{\partial y^2}
+\frac{\partial^2 u}{\partial z^2}
=-\frac{G}{\mu}.
$$

The no-slip boundary conditions are

$$
u(y,0)=0,
\qquad
u(y,h)=U,
\qquad
u\left(-\frac{w}{2},z\right)
=u\left(\frac{w}{2},z\right)=0.
$$

At the two upper corners, the prescribed top-wall velocity and stationary side-wall velocity are discontinuous. The series below satisfies the boundary values everywhere except at those corner points, where it converges in the usual Fourier sense.

## Exact velocity field

Because the governing equation is linear, write

$$
u(y,z)=u_C(y,z)+u_P(y,z),
$$

where $u_C$ is the wall-driven rectangular Couette solution and $u_P$ is the pressure-driven rectangular Poiseuille solution.

### Rectangular Couette contribution

Define

$$
\lambda_m=\frac{(2m+1)\pi}{w},
\qquad m=0,1,2,\ldots
$$

Then

$$
u_C(y,z)=
\frac{4U}{\pi}
\sum_{m=0}^{\infty}
\frac{(-1)^m}{2m+1}
\frac{\sinh(\lambda_m z)}{\sinh(\lambda_m h)}
\cos(\lambda_m y).
$$

This term satisfies Laplace's equation, vanishes at $z=0$ and $y=\pm w/2$, and equals $U$ on the interior of the upper wall.

### Rectangular Poiseuille contribution

For odd positive integers $n=1,3,5,\ldots$,

$$
u_P(y,z)=
\frac{4Gh^2}{\mu\pi^3}
\sum_{\substack{n=1\\n\;\mathrm{odd}}}^{\infty}
\frac{1}{n^3}
\left[
1-
\frac{\cosh\left(n\pi y/h\right)}
{\cosh\left(n\pi w/(2h)\right)}
\right]
\sin\left(\frac{n\pi z}{h}\right).
$$

This term vanishes on all four walls and satisfies

$$
\nabla_{y,z}^{2}u_P=-\frac{G}{\mu}.
$$

### Combined result

The exact fully developed solution is therefore

$$
\boxed{
\begin{aligned}
u(y,z)={}&
\frac{4U}{\pi}
\sum_{m=0}^{\infty}
\frac{(-1)^m}{2m+1}
\frac{\sinh\left((2m+1)\pi z/w\right)}
{\sinh\left((2m+1)\pi h/w\right)}
\cos\left(\frac{(2m+1)\pi y}{w}\right)
\\[4pt]
&+
\frac{4Gh^2}{\mu\pi^3}
\sum_{\substack{n=1\\n\;\mathrm{odd}}}^{\infty}
\frac{1}{n^3}
\left[
1-
\frac{\cosh\left(n\pi y/h\right)}
{\cosh\left(n\pi w/(2h)\right)}
\right]
\sin\left(\frac{n\pi z}{h}\right).
\end{aligned}
}
$$

The signs of $U$ and $G$ determine whether the two driving mechanisms assist or oppose one another.

## Volumetric flow rate

The total flow rate is

$$
Q=Q_C+Q_P,
$$

with

$$
Q_C=
\frac{8Uw^2}{\pi^3}
\sum_{m=0}^{\infty}
\frac{
\tanh\left((2m+1)\pi h/(2w)\right)
}{(2m+1)^3},
$$

and

$$
Q_P=
\frac{Gwh^3}{12\mu}
\left[
1-
\frac{192h}{\pi^5w}
\sum_{\substack{n=1\\n\;\mathrm{odd}}}^{\infty}
\frac{
\tanh\left(n\pi w/(2h)\right)
}{n^5}
\right].
$$

The cross-sectional mean velocity is

$$
\bar{u}=\frac{Q}{wh}.
$$

## Limiting-case checks

These limits are useful for checking the COMSOL model and the series implementation.

### No pressure gradient

If $G=0$, then $u=u_C$: finite-width rectangular Couette flow.

### Stationary upper wall

If $U=0$, then $u=u_P$: pressure-driven flow in a rectangular duct.

### Infinite-width limit

Far from the side walls, or as $w/h\rightarrow\infty$,

$$
u(y,z)\rightarrow
U\frac{z}{h}
+\frac{G}{2\mu}z(h-z),
$$

and

$$
Q\rightarrow
\frac{Uwh}{2}
+\frac{Gwh^3}{12\mu}.
$$

This is the plane Couette-Poiseuille result. It is not the exact result for a finite rectangular channel because it omits the side-wall no-slip condition.

### Reversed lower-wall convention

If the lower wall at $z=0$ moves and the upper wall is stationary, replace $z$ by $h-z$ in $u_C$. If a wall moves in the negative $x$ direction, use a negative value of $U$.

## COMSOL validation

1. Use the same $w$, $h$, $L$, $U$, $\mu$, $p_{\mathrm{in}}$, and $p_{\mathrm{out}}$ in COMSOL and in the series.
2. Confirm that the moving wall is at $z=h$ and moves in the $+x$ direction.
3. Confirm no slip at $z=0$ and $y=\pm w/2$.
4. Compare $u_x(y,z)$ on a cross-section sufficiently far from inlet and outlet effects. For a fully developed model, the field should be independent of $x$.
5. Truncate each series only after the velocity and flow rate stop changing to the required tolerance. More terms are needed near the upper corners.
6. Exclude a very small neighborhood around the upper corners from pointwise error tests because the ideal boundary data are discontinuous there.
7. Compare the numerical and analytical flow rates and, if desired, compute

$$
\varepsilon_{L^2}=
\left[
\frac{
\displaystyle\int_A
\left(u_{\mathrm{COMSOL}}-u_{\mathrm{series}}\right)^2\,dA
}{
\displaystyle\int_A u_{\mathrm{series}}^2\,dA
}
\right]^{1/2}.
$$

The wall shear components follow from

$$
\tau_{xy}=\mu\frac{\partial u}{\partial y},
\qquad
\tau_{xz}=\mu\frac{\partial u}{\partial z}.
$$

## Files

- COMSOL model: `rectangular-couette-poiseuille-flow.mph`
- Full derivation: [Rectangular Couette-Poiseuille Flow - Analytical Solution (PDF)](../Rectangular%20Couette-Poiseuille%20flow%20Analytical%20Solution.pdf)

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
