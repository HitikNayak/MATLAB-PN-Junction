# Numerical Solution of Poisson's Equation in a Silicon P-N Junction Using MATLAB

A numerical analysis of an abrupt silicon p-n junction using the **Finite Difference Method (FDM)** in MATLAB. The project calculates the electrostatic potential and electric field and compares the numerical results with the analytical depletion approximation.

## Project Overview

This project focuses on solving the one-dimensional Poisson's equation for an abrupt silicon p-n junction under the depletion approximation.

The finite difference method is used to discretize Poisson's equation and calculate the electrostatic potential across the junction. The electric field is then obtained by differentiating the potential numerically.

The numerical results are compared with the analytical depletion approximation to evaluate the accuracy of the numerical solution.

## Objectives

* Develop a one-dimensional mesh for an abrupt silicon p-n junction.
* Construct the space-charge density profile using the depletion approximation.
* Discretize and solve Poisson's equation using the finite difference method.
* Calculate the electrostatic potential distribution.
* Determine the electric field from the potential gradient.
* Calculate the depletion widths and built-in potential.
* Compare numerical results with analytical solutions.

## Device Parameters

The following parameters are used for the simulation:

| Parameter | Symbol | Value |
|---|---|---|
| Acceptor concentration | N<sub>A</sub> | 1 &times; 10<sup>15</sup> cm<sup>-3</sup> |
| Donor concentration | N<sub>D</sub> | 1 &times; 10<sup>16</sup> cm<sup>-3</sup> |
| Intrinsic carrier concentration | n<sub>i</sub> | 1 &times; 10<sup>10</sup> cm<sup>-3</sup> |
| Temperature | T | 300 K |
| Relative permittivity of silicon | &epsilon;<sub>r</sub> | 11.7 |
| Number of mesh points | N | 4001 |

## Theoretical Background

### 1. Poisson's Equation

The one-dimensional Poisson's equation is given by:

$$
\frac{d^2 V(x)}{dx^2}=-\frac{\rho(x)}{\epsilon_{Si}}
$$

where:

* $V(x)$ is the electrostatic potential.
* $\rho(x)$ is the space-charge density.
* $\epsilon_{Si}$ is the permittivity of silicon.

The electric field is calculated as:

$$
E(x)=-\frac{dV(x)}{dx}
$$

### 2. Depletion Approximation

Under the depletion approximation, the mobile carriers are assumed to be absent in the depletion region. The charge density is determined by the ionized dopant atoms.

For the p-side:

$$
\rho(x)=-qN_A
$$

For the n-side:

$$
\rho(x)=qN_D
$$

Outside the depletion region, the charge density is assumed to be zero.

### 3. Built-in Potential

The built-in potential at thermal equilibrium is calculated using:

$$
V_{bi}=\frac{kT}{q}\ln\left(\frac{N_A N_D}{n_i^2}\right)
$$

### 4. Depletion Width

The total depletion width is:

$$
W=\sqrt{\frac{2\epsilon_{Si}}{q}
\left(\frac{1}{N_A}+\frac{1}{N_D}\right)V_{bi}}
$$

The depletion widths on the p-side and n-side are:

$$
x_p=\frac{N_D}{N_A+N_D}W
$$

$$
x_n=\frac{N_A}{N_A+N_D}W
$$

## Numerical Methodology

The simulation is performed using the following steps:

1. **Define physical constants:** Specify the electronic charge, Boltzmann constant, silicon permittivity, temperature, and doping concentrations.
2. **Calculate analytical parameters:** Determine the built-in potential, depletion widths, and maximum electric field.
3. **Generate the mesh:** Create a uniform one-dimensional mesh with 4001 points, extending beyond the depletion region into the neutral regions.
4. **Construct the charge density:** Assign the space-charge density according to the depletion approximation.
5. **Solve Poisson's equation:** Use the finite difference method to discretize the governing equation and calculate the electrostatic potential.
6. **Calculate the electric field:** Obtain the electric field by numerically differentiating the potential.
7. **Validate the results:** Compare the numerical solution with the analytical depletion approximation and calculate the percentage error.
8. **Plot the results:** Generate graphs of the junction structure, charge density, electrostatic potential, and electric field.

## Simulation Results

### Analytical and Numerical Comparison

| Parameter              | Analytical Result | Numerical Result |   Error |
| ---------------------- | ----------------: | ---------------: | ------: |
| Built-in potential     |        0.655029 V |       0.656756 V | 0.2636% |
| Total depletion width  |         0.9653 µm |        0.9648 µm | 0.0591% |
| P-side depletion width |         0.8776 µm |        0.8773 µm | 0.0325% |
| N-side depletion width |         0.0878 µm |        0.0875 µm | 0.3250% |
| Maximum electric field |     13571.18 V/cm |    13569.31 V/cm | 0.0137% |

### Results and Discussion

The numerical solution shows close agreement with the analytical depletion approximation.

The depletion region extends farther into the lightly doped p-side than into the heavily doped n-side, consistent with the charge-neutrality condition.

The maximum electric field occurs at the metallurgical junction. The largest reported percentage error among the calculated parameters is 0.3250%, corresponding to the n-side depletion width.

These results demonstrate the application of the finite difference method to the numerical analysis of a semiconductor p-n junction.

## Simulation Plots

The MATLAB program generates the following plots:

1. **Junction Structure:** One-dimensional mesh showing the metallurgical junction and depletion-region boundaries.
2. **Charge Density:** Space-charge density distribution across the p-n junction.
3. **Electrostatic Potential:** Numerical potential distribution across the junction.
4. **Electric Field:** Electric field distribution obtained from the numerical potential.

## Tools and Technologies

* **MATLAB:** Numerical computation and visualization.
* **Finite Difference Method:** Numerical solution of Poisson's equation.
* **Semiconductor Device Physics:** Depletion approximation and p-n junction analysis.

No additional MATLAB toolboxes are required.

## How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/hitiknayak/MATLAB-PN-Junction.git
   ```

2. Navigate to the project directory:

   ```bash
   cd MATLAB-PN-Junction
   ```

3. Open the MATLAB script in MATLAB.

4. Run the script to calculate the junction parameters and generate the simulation plots.


## Applications

* Numerical analysis of semiconductor devices.
* Understanding the electrostatic properties of p-n junctions.
* Studying charge density, potential, and electric field distributions.
* Learning finite difference methods for semiconductor device modelling.

## Author

**Hitik Kumar Nayak**
M.Tech, Microelectronics and VLSI
Indian Institute of Technology Bhilai

---

**Project:** Semiconductor Devices Modelling
**Topic:** Numerical Solution of Poisson's Equation in a p-n Junction Using MATLAB
