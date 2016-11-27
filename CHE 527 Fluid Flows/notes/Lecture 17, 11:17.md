# Lecture 17 COMSOL Multiphysics 5.2a
James Wilkes, 2016-11-17

1. select *Model Wizard*
2. under *Select Physics* $\to$ Fluid Flow $\to$ *Porous Media and Subsurface Flow* $\to$ *D'Arcy's law*, click *Add* *Mathematics* $\to$ *PDE*
3. under *Select Study* $\to$ preset studies $\to$ stationary, click done.

### Building the model

* Add *parameters* under *Global Definitions*
* Add *Geometry* under *Component*
* under *Darcy's Law* $\to$ *Fluid and Matrix Properties*
    * Temperature (default): user defined: 293.15[K]
    * Material: water
    * Porosity: user defined: 0.20
    * Permeability: user defined: 0.986*10ˆ-10 [m^2]
* Add *pressure* under *Darcy's Law*
    * add left side presure
    * add right side pressure
* In *Mesh* select *finer*, click *Build All*
* *Study* $\to$ *Compute*
* under *Results*, pick *2D Plot Group* 
    * *Contour*
    * *Arrow Surface*