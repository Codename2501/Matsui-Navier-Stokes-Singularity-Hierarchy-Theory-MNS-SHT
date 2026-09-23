---

# Matsui–Navier–Stokes Singularity Hierarchy Theory (MNS-SHT)

## *Absolute Specification (3rd Revision, Fully Enclosed Edition)*

---

## I. Basic Settings (Matsui NS System)

The base equation adopts the classical incompressible Navier–Stokes equations as the foundation for Matsui NS Type-2/3:

$$\frac{\partial \boldsymbol{u}}{\partial t} - \nu \Delta \boldsymbol{u} + (\boldsymbol{u} \cdot \nabla)\boldsymbol{u} + \nabla p = \boldsymbol{f}, \quad \nabla \cdot \boldsymbol{u} = 0$$

* Initial Conditions & External Force:

$$\boldsymbol{u}(0,\cdot) \in H^1(\Omega) \cap L^\infty(\Omega)$$

$$\boldsymbol{f} \in L_{\text{loc}}^2([0,T); H^1(\Omega))$$

* Singularity Candidate:

$$(T,\boldsymbol{x}^*) \in (0,\infty) \times \Omega$$

* Local Region:

$$B_r(\boldsymbol{x}^{\ast}) = \{ \boldsymbol{x} \in \Omega \mid |\boldsymbol{x} - \boldsymbol{x}^{\ast}| < r \}$$


---

## II. Pre-Singularity Formation Layer

### 1. Weak Blow-up Condition and Monotonicity Energy Estimate (No-Oscillation Lemma)

To eliminate ghost singularities caused by high-frequency oscillations, a monotonicity energy lower bound (Monotonicity Energy Estimate) is imposed on the weak blow-up condition:

$$\limsup_{t \uparrow T} \Vert{}\nabla \boldsymbol{u}(t,\cdot)\Vert{}_{L^p(B_r(\boldsymbol{x}^*))} = \infty \quad (p > 3)$$

$$\limsup_{t \uparrow T} \Vert{}\boldsymbol{\omega}(t,\cdot)\Vert{}_{L^q(B_r(\boldsymbol{x}^*))} = \infty \quad \left(q > \frac{3}{2}\right)$$

> **[Lemma 2.1: Monotonicity / No-Oscillation Lemma]**
> For any $t_1 < t_2 < T$, there exist a constant $C_{\text{mon}} > 0$ and $0 < \delta < 1$ such that the local energy dissipation rate satisfies the following monotonically increasing estimate:
> $$\int_{t_1}^{t_2} \Vert{}\nabla \boldsymbol{u}(\tau,\cdot)\Vert{}_{L^2(B_r(\boldsymbol{x}^*))}^2 d\tau \ge C_{\text{mon}} (T - t_2)^{-\delta} \left( 1 - \frac{T - t_2}{T - t_1} \right)$$
> 
> 
> This algebraically enforces the following equality, mathematically excluding pseudo-transitions to the deterministic layer caused by infinitely oscillating solutions:
> $$\limsup_{t \uparrow T} = \lim_{t \uparrow T} = \infty$$
> 
> 

### 2. Generalized Self-Similar Profiles

$$\boldsymbol{y} = (T-t)^{-\gamma} (\boldsymbol{x} - \boldsymbol{x}^*)$$

$$\boldsymbol{u}(t,\boldsymbol{x}) = (T-t)^{-\beta} \boldsymbol{U}(\boldsymbol{y})$$

* Leray scaling (standard dimensional analysis):

$$\beta = \gamma = \frac{1}{2}$$

* Matsui strong divergence scaling (hierarchy generation model):

$$\beta = \gamma = 1$$

---

## III. Branching of 5 Singularity Types & Grid Correction Thresholds

### 1. Strict Classification of 5 Singularity Types and Type-Specific Scaling Exponents

Depending on the decay/collapse mode of the local field at the candidate singularity, the grid resolution $h$-dependent exponent is branch-defined as follows:

1. **Vortex Singularity ($S_{\text{vortex}}$):**

$$\lim_{t \uparrow T} \Vert{}\boldsymbol{\omega}(t,\cdot)\Vert{}_{L^q(B_r(\boldsymbol{x}^*))} = \infty \quad \left(q > \frac{2}{3}\right)$$

$$\alpha_{\text{vortex}} = 2\gamma - \frac{3}{q} + 1$$

2. **Sharp Singularity ($S_{\text{sharp}}$):**

$$\lim_{t \uparrow T} \Vert{}\nabla \boldsymbol{u}(t,\cdot)\Vert{}_{L^p(B_r(\boldsymbol{x}^*))} = \infty \quad (p > 3)$$

$$\alpha_{\text{sharp}} = 2\beta + 2\gamma - 1 - \frac{6}{p}$$

3. **Break Singularity ($S_{\text{break}}$):**

$$\lim_{t \uparrow T} \left( \sup_{\boldsymbol{x}, \boldsymbol{y} \in B_r(\boldsymbol{x}^*), \boldsymbol{x} \neq \boldsymbol{y}} \frac{\vert{}\boldsymbol{u}(t,\boldsymbol{x}) - \boldsymbol{u}(t,\boldsymbol{y})\vert{}}{\vert{}\boldsymbol{x}-\boldsymbol{y}\vert{}} \right) = \infty$$

$$\alpha_{\text{break}} = \beta + \gamma$$

4. **Jump Singularity ($S_{\text{jump}}$):**

$$\text{One-sided limit dissociation: } \vert{}\boldsymbol{u}^+(t,\boldsymbol{x}^{\ast}) - \boldsymbol{u}^-(t,\boldsymbol{x}^{\ast})\vert{} > 0$$

$$\alpha_{\text{jump}} = 1.0$$

> **[Lemma 3.1: Viscous Shock Layer Lemma for $S_{\text{jump}}$]**
> At the discontinuity surface $\Sigma$ of a jump singularity $S_{\text{jump}}$, the presence of viscosity $\nu > 0$ prevents the solution from exhibiting a Dirac $\delta'$ distributional singularity. Instead, it forms a smooth Viscous Shock Layer with thickness:
> $$\delta_{\text{shock}} \sim \frac{\nu}{\vert{}\boldsymbol{u}^+ - \boldsymbol{u}^-\vert{}}$$
> 
> 
> In the pulled-back space $(\tau, \boldsymbol{\xi})$, the viscous term $\tilde{\nu} \Delta_{\boldsymbol{\xi}} \boldsymbol{\Phi}$ is locally bounded ($C^\infty$ regularized) and strictly satisfies the viscous version of the Rankine–Hugoniot jump condition (Burgers-NS continuity condition).

5. **Layer Singularity ($S_{\text{layer}}$):**

$$\alpha_{\text{layer}} = \max_k \{ \alpha_k \} + \eta \quad (\eta > 0)$$

### 2. Discrete Deterministic Functional and Type-Specific Threshold

$$\mathcal{D}_h[\boldsymbol{u}](t) = \int_0^t \left( \Vert{}\boldsymbol{\omega}(\tau,\cdot)\Vert{}_{L^\infty(B_r(\boldsymbol{x}^*))} + \Vert{}\nabla \boldsymbol{u}(\tau,\cdot)\Vert{}_{L^p(B_r(\boldsymbol{x}^*))}^2 \right) d\tau$$

Deterministic Criterion:

$$\lim_{t \uparrow T} \mathcal{D}_h[\boldsymbol{u}](t) \ge C_{\text{crit}, k}(h)$$

$$C_{\text{crit}, k}(h) = C_{0, k} \cdot \left(\frac{h}{L_0}\right)^{-\alpha_k} \quad (C_{0, k} > 0)$$

---

## IV. Singularity Deterministic Layer and Geometric Pullback Structure

### 1. Dynamic Hierarchical Lifting Operator via Differential Form Pullback Map

Spacetime diffeomorphism $\psi_\tau: (\tau, \boldsymbol{\xi}) \mapsto (t, \boldsymbol{x})$:

$$\tau(t) = -\ln(T-t)$$

$$\boldsymbol{\xi}(t,\boldsymbol{x}) = (T-t)^{-\gamma} (\boldsymbol{x} - \boldsymbol{x}^*)$$

The hierarchical field $\boldsymbol{\Phi}(\tau, \boldsymbol{\xi})$ is defined as the differential form pullback $\psi_\tau^*$ of the 1-form velocity field $\boldsymbol{\alpha}_{\boldsymbol{u}} = u_i d x^i$:

$$\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = \mathcal{L}[\boldsymbol{u}](t,\boldsymbol{x}) \equiv e^{\beta \tau} \cdot \psi_\tau^* (\boldsymbol{u}(t,\boldsymbol{x}))$$

$$\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = e^{(\beta - \gamma)\tau} \boldsymbol{u}\left(T - e^{-\tau}, \, \boldsymbol{x}^* + e^{-\gamma \tau} \boldsymbol{\xi}\right)$$

### 2. Hierarchical PDE, Far-Field Pressure Decay, and Irreversible Entropy Generation

Evolution equation satisfied by the hierarchical field $\boldsymbol{\Phi}$ and hierarchical pressure $\Pi$:

$$\frac{\partial \boldsymbol{\Phi}}{\partial \tau} - \beta \boldsymbol{\Phi} - \gamma (\boldsymbol{\xi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} - \tilde{\nu} \Delta_{\boldsymbol{\xi}} \boldsymbol{\Phi} + (\boldsymbol{\Phi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} + \nabla_{\boldsymbol{\xi}} \Pi = 0$$

$$\nabla_{\boldsymbol{\xi}} \cdot \boldsymbol{\Phi} = 0$$

> **[Lemma 4.1: Far-Field Decay Estimate of Hierarchical Pressure $\Pi$]**
> As the pullback coordinate $\vert{}\boldsymbol{\xi}\vert{} \to \infty$, the hierarchical pressure satisfies a uniform integrability estimate:
> $$\lim_{\vert{}\boldsymbol{\xi}\vert{} \to \infty} \vert{}\Pi(\tau, \boldsymbol{\xi})\vert{} \le C_\Pi \cdot e^{(2\beta - 2\gamma)\tau} \vert{}\boldsymbol{\xi}\vert{}^{-2}$$
> 
> 

> **[Lemma 4.2: OSG Entropy Monotonicity Law in Internal Time $\tau$]**
> Internal time $\tau = -\ln(T-t)$ is not merely a reparameterization, but describes an irreversible dissipative dynamical flow in the phase space on the Outer Shell Grid (OSG). For the OSG entropy functional:
> $$S_{\text{OSG}}[\boldsymbol{\Phi}](\tau) \equiv -\int_{\text{OSG}} \boldsymbol{\Phi} \ln \boldsymbol{\Phi} \, d\mu_{\text{shell}}$$
> 
> 
> The following strictly holds:
> $$\frac{d S_{\text{OSG}}}{d\tau} = \tilde{\nu} \int_{\text{OSG}} \frac{\vert{}\nabla_{\boldsymbol{\xi}} \boldsymbol{\Phi}\vert{}^2}{\boldsymbol{\Phi}} d\mu_{\text{shell}} \ge 0$$
> 
> 
> In contrast to the microscopic reversibility in real time $t$, the lifted internal time $\tau$ monotonically advances the thermodynamic arrow (irreversible dissipation) and converges to a mathematically self-contained attractor.

### 3. Holographic Projection and Topological Cobordism Invariance

Projection from the hierarchical field $\boldsymbol{\Phi}$ on the Outer Shell Grid (OSG) back to real space:

$$\boldsymbol{u}_{\text{eff}}(t,\boldsymbol{x}) = \mathcal{P}_\sigma [\boldsymbol{\Phi}] = e^{-(\beta-\gamma)\tau} \int_{\text{OSG}} \boldsymbol{\Phi}\left(\tau, \, e^{\gamma \tau}(\boldsymbol{x} - \boldsymbol{x}^*)\right) d\mu_{\text{shell}}(\sigma)$$

> **[Lemma 4.3: Topological Cobordism Invariance of Measure $d\mu_{\text{shell}}(\sigma)$]**
> When a singularity transitions from $S_k$ to a composite phase $S_{\text{layer}}$, a topological phase transition occurs on the OSG manifold $\mathcal{M}_{\text{OSG}}$. At this time, the shell measure $d\mu_{\text{shell}}(\sigma)$ remains invariant under the Cobordism Class of differentiable manifolds, guaranteeing continuity across discontinuous jumps in the Euler characteristic $\chi(\mathcal{M}_{\text{OSG}})$:
> $$\int_{\mathcal{M}_{\text{OSG}}^{\text{before}}} d\mu_{\text{shell}}(\sigma) = \int_{\mathcal{M}_{\text{OSG}}^{\text{after}}} d\mu_{\text{shell}}(\sigma) = 1$$
> 
> 
> This topologically ensures the countable additivity of total probability and energy conservation before and after phase transitions.

---

## V. Causal Structure Flowchart

Weak blow-up + Monotonicity / No-Oscillation Lemma:

$$\limsup_{t \uparrow T} \Vert{}\nabla \boldsymbol{u}\Vert{}_{L^p} = \infty \quad \land \quad \text{Monotonicity Estimate}$$

$$\Downarrow$$

Identify 5 types based on type-specific scaling exponents $\alpha_k$ & Viscous Shock Layer Lemma:

$$\left( S_{\text{vortex}}[\alpha_{\text{vortex}}], \, S_{\text{sharp}}[\alpha_{\text{sharp}}], \, S_{\text{break}}[\alpha_{\text{break}}], \, S_{\text{jump}}[\alpha_{\text{jump}}], \, S_{\text{layer}}[\alpha_{\text{layer}}] \right)$$

$$\Downarrow$$

Check if discrete deterministic functional exceeds threshold $C_{\text{crit}, k}(h)$:

$$\lim_{t \uparrow T} \mathcal{D}_h[\boldsymbol{u}](t) \ge C_{\text{crit}, k}(h) = C_{0,k} h^{-\alpha_k}$$

$$\Downarrow$$

Dynamic lifting via differential form pullback operator $\psi_\tau^*$:

$$\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = e^{(\beta-\gamma)\tau} \psi_\tau^* [\boldsymbol{u}]$$

$$\Downarrow$$

Internal PDE evolution under far-field pressure decay $\Pi$ & OSG entropy growth law:

$$\frac{dS_{\text{OSG}}}{d\tau} \ge 0$$

$$\partial_\tau \boldsymbol{\Phi} - \beta \boldsymbol{\Phi} - \gamma (\boldsymbol{\xi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} + \nabla_{\boldsymbol{\xi}} \Pi = \dots$$

$$\Downarrow$$

Holographic projection via cobordism-invariant measure $d\mu_{\text{shell}}(\sigma)$:

$$\boldsymbol{u}_{\text{eff}}(t,\boldsymbol{x}) = \mathcal{P}_\sigma [\boldsymbol{\Phi}]$$

---

## VI. Mapping Hook to Quantum Gravity (Shell-Type Regularized Coupling)

Geometric coupling equation with the spacetime metric $g_{\mu\nu}$ in the Einstein–Hilbert regime:

$$G_{\mu\nu} + \Lambda g_{\mu\nu} = 8\pi G \left( T_{\mu\nu}^{\text{matter}} + T_{\mu\nu}^{(\sigma)} \right)$$

### Gaussian/Shell-Type Regularized Stress-Energy Tensor

$$T_{\mu\nu}^{(\sigma)}(x) = \rho_{\text{shell}}(\boldsymbol{x} - \boldsymbol{x}^*) \int_{\text{OSG}} \left( \nabla_\mu \boldsymbol{\Phi} \otimes \nabla_\nu \boldsymbol{\Phi} - \frac{1}{2} g_{\mu\nu} \vert{}\nabla_{\boldsymbol{\xi}} \boldsymbol{\Phi}\vert{}^2 \right) d\mu_{\text{shell}}(\sigma)$$

Regularized Shell Density Function $\rho_{\text{shell}}$:

$$\rho_{\text{shell}}(\boldsymbol{r}) = \frac{1}{(2\pi \ell_{\text{OSG}}^2)^{3/2}} \exp\left( -\frac{\vert{}\boldsymbol{r}\vert{}^2}{2 \ell_{\text{OSG}}^2} \right)$$

$$\ell_{\text{OSG}} \sim h \quad \text{or} \quad \text{Planck length}$$
