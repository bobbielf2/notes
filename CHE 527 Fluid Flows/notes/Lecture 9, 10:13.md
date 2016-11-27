# Lecture 9, Inviscid and Irrotational flows (ct'd)

(Wilkes. pp. 67-96; Chapter 7)

# Last time:
### Is the N-S equation frame-invariant?

* Is there any effect of a rotation of frame on the stress or pressure? (Yes! The *Coriolis force* and *centrifugal force*!)
* In a rotating frame, a vector $\mathbf{v}$ is going to be changing within the frame: $$\mathbf{v} = \hat{\mathbf{v}}\cdot\mathbf{Q}(t)$$ where $\mathbf{Q}(t)$ is the tensor that describes the rotational motion of the frame with respect to the inertial frame.
* Then the inertia term in the N-S equation becomes: $$\frac{D\mathbf{v}}{Dt} = \frac{D\hat{\mathbf{v}}}{Dt}\cdot\mathbf{Q}+2\boldsymbol\omega\times\hat{\mathbf{v}}\cdot\mathbf{Q}+\boldsymbol\omega\times(\boldsymbol\omega\times\hat{\mathbf{r}})\cdot\mathbf{Q}$$ In the above equality, we identify the **Coriolis force** (stress): $2\boldsymbol\omega\times\hat{\mathbf{v}}$, and the **centrifugal force** (stress): $\boldsymbol\omega\times(\boldsymbol\omega\times\hat{\mathbf{r}})$.
* So the N-S equation in a rotating frame (steady rotation) is $$\frac{D\hat{\mathbf{v}}}{Dt} = \hat{\mathbf{g}} - \frac{1}{\rho}\hat{\nabla P}-2\boldsymbol\omega\times\hat{\mathbf{v}} - \boldsymbol\omega\times(\boldsymbol\omega\times\hat{\mathbf{r}})+ \hat{\nabla}\cdot\hat{\boldsymbol\tau}$$ Note that the constitutive equation $\hat{\nabla}\cdot\hat{\boldsymbol\tau}$ is frame-invariant, but the inertia is not.

# Continue:

* Example 1: Stationary Particle,  put in rotating frame
* Example 2: Planetary System,  circular orbit, Inertial Frame 
* Example 3: Planetary System,  circular orbit, Rotating Frame 

### Coriolis "force"


### Steady, Two-Dimensional, Incompressible, Irrotational Flow

* potential flow = irrotational flow = linearity