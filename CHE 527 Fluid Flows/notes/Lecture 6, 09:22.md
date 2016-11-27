# Lecture 6

#### Mass, Momentum & Mechanical Energy Balances
(Deen, pp. 26-35, 220-227; Wilkes Chap 2)

Mass x acceleration = body force + surface force

$$\int_{V(t)}\rho\frac{D\mathbf{v}}{Dt}\,dV = \int_{V(t)}\rho \mathbf{g}\,dV + \int_{S(t)}\mathbf{n}\cdot\boldsymbol\sigma\,dS $$

applying divergence theorem, shrink control volume $V(t)\to 0$, we have

$$\rho\frac{D\mathbf{v}}{Dt} = \rho \mathbf{g} + \nabla\cdot\boldsymbol\sigma$$

- Stress tensor $\boldsymbol\sigma$ is *symmetric*, $\sigma_{ij} = \sigma_{ji}$
    - this is due to *conservation of angular momentum* for each fluid element.
    - exceptions: ferrofluids, liquid crystals

    
#### Constitutive Equtions
(Deen, pp. 227-230, 236-242, 250-252; Wilkes Chap 11)

##### Types of fluid constitutive laws:

1. Inviscid fluid
    - $\boldsymbol\sigma = -P\boldsymbol\delta$ (no shear)
    - $$\rho\frac{D\mathbf{v}}{Dt} = \rho \mathbf{g} - \nabla P$$
    - Archimedes' principle (Archimedes invented lever, catapult, almost invented calculus)2. Newtonian viscous fluid
    - Newton's proposal: stress tensor is a linear function of velocity gradient
    - Newtonian stress tensor: $\boldsymbol\tau = 2\mu\mathbf{D} + (\kappa - \frac{2}{3}\mu)\,(\nabla\cdot\mathbf{v})\,\boldsymbol\delta$3. Generalized Newtonian fluid
    - general inelastic fluid: $\boldsymbol\tau = a_1\boldsymbol\delta + a_2\mathbf{D}+a_3\mathbf{D}\cdot\mathbf{D}$ (Reiner-Rivlin fluid)4. Binghamplastic
    - stress tensor is a non-linear function of the deformation gradient5. Elastic fluid (UCM fluid)
    - stress goes to zero *gradually*
    - need to include time derivative of stress $\frac{d}{dt}\boldsymbol\tau$
    - Simple model for the stress with memory: $$\lambda \frac{d}{dt}\boldsymbol\tau + \boldsymbol\tau = \mu\dot{\gamma},$$ where $\lambda$ = relaxation time.
    - Solution for startup of shear at time $0$: $$\boldsymbol\tau = \mu\dot{\gamma}(1-e^{-t/\lambda})$$
    - Cessation of shear after attaining steady state at time $0$: $$\boldsymbol\tau = \mu\dot{\gamma}\;e^{-t/\lambda}$$6. Simple elastic solid