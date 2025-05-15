# AE370Project2
This project models the dynamic interaction between a train pantograph and an electrified catenary wire using numerical methods. We aim to determine how key factors — including train speed, wire tension, damping, and thermal effects, influence critical speed, contact stability, and overall system performance in high-speed rail systems.

# Project Contributions
**A. Rohan S. Kumar Rskumar2@illinois.edu**
I was responsible for Section (4), which presented and analyzed the simulation results. My primary contributions involved generating visualizations that examined how vertical displacement of the catenary wire was influenced by pantograph speed, ambient temperature, and dropper configuration. I constructed Python scripts to process numerical output from the Newmark-$\beta$ solver and create plots that highlighted key trends in the system's dynamic response. I also wrote detailed technical interpretations of the plots, tying the observed behaviors back to the governing equations and the original research questions. Overall, I contributed approximately 23\% of the project, with a focus on data interpretation, technical writing, and final integration of the analysis.


**B. Luke H. McNamara Lukem4@illinois.edu**
I contributed to the mathematical derivation in Section (2), which outlines the governing equations and numerical formulation. I also used ChatGPT to help identify a relevant application topic and determine an appropriate numerical method for our system. Through that process, I explored different integration schemes and confirmed that the Newmark-$\beta$ method was best suited for second-order, stiff problems like ours. In addition, I helped with formatting the LaTeX document, organizing the report, and finalizing the nomenclature. Overall, I contributed approximately 30\% of the project, including both technical content and report preparation.


**C. Alex Roskov aroskov@illinois.edu**
I was primarily responsible for the introduction as in accordance with the requirements of Section (1). Consequently, I was responsible for the written content of the section which included the selection of the IBVP for this project and determining the directions this project would take. Given my background in railway engineering, I also helped the rest of the team get up to speed with the concepts involved in the dynamical system and conducted any more necessary research to define our system. I discussed with ChatGPT to lock in a dynamical system, suggest questions we could study with the system and also used it to correct grammar and tone in my writing. Overall, I contributed approximately 22\% to the overall project.


**D. Ella M. Young ellamy2@illinois.edu**
I was responsible for the implementation section, where I developed and coded the simulation scenarios used to model the pantograph–catenary interaction. This included applying the Newmark-$\beta$ method to approximate system behavior under varying conditions such as temperature and train speed. I also conducted an error convergence study to assess the accuracy and stability of our numerical approach. In addition, I created the GitHub repository to organize and share the project code, and contributed to writing both the abstract and the conclusion. I used ChatGPT to assist with Python coding and refining the clarity of my writing throughout the report. Overall, I contributed approximately 25\% to the project.

# Motivation 
Modern high-speed rail systems rely on overhead catenary wires to deliver continuous electrical power to trains via a pantograph. At high velocities, even minor dynamic instabilities in this wire–pantograph interaction can lead to contact loss, electrical arcing, mechanical wear, and operational inefficiency.
As global infrastructure shifts toward electrified and sustainable transportation, understanding and optimizing these systems is critical, especially as speeds increase and safety requirements tighten.
This project was motivated by the following goals:
- Investigate critical speed thresholds at which pantograph contact becomes unstable
- Model the physics of the wire as a tensioned, damped structure influenced by a moving load
- Evaluate how variables like damping, wire tension, and temperature affect contact quality
- Apply and validate a robust time integration method (Newmark-β) in a dynamic, real-world scenario
- Generate insight into how numerical modeling can inform the engineering design of high-speed rail systems
Ultimately, this project bridges theoretical numerical methods with applied transportation engineering, using simulation to gain intuition and guide better system performance in real-world catenary infrastructure.

# Key Features
This project combines physical modeling, numerical analysis, and data visualization to simulate and evaluate the dynamic behavior of high-speed railway overhead systems. Below are the key features that make this simulation both rigorous and insightful:

**Physics-Based Modeling**
Simulates the vertical dynamics of a catenary wire under a moving pantograph using a second-order partial differential equation (PDE)

Includes realistic system parameters such as wire tension, mass density, damping, and moving uplift force

**Newmark-β Time Integration**
Implements the Newmark-β method for time integration, offering:

Second-order accuracy

Unconditional stability for linear systems

Suitability for stiff, second-order ODEs like those found in structural dynamics

**Convergence Analysis**
Performs log-log spatial and temporal convergence studies to validate numerical accuracy

Estimates convergence rates using linear regression on error data

**Local Truncation Error Evaluation**
Computes local truncation error (LTE) over time to assess the per-step accuracy of the method

Visualizes LTE trends to evaluate numerical stability and method behavior

**Physical Insight Through Visualization**
Plots:

Displacement under the pantograph over time

Contact gap between wire and pantograph

Total vibrational energy in the system

All plots help assess physical realism and critical performance thresholds

**Clean & Modular Code**
Written in Python with NumPy, SciPy, and Matplotlib

Organized to support parameter studies and method validation

Integrated with explanatory Markdown cells in a well-documented Jupyter Notebook

## Assumptions
To keep the simulation computationally efficient and analytically focused, several simplifying assumptions were made. These allow us to isolate key physical behaviors while maintaining tractability:

**Physical Modeling Assumptions**
Single-span wire: Only one catenary span is modeled, neglecting coupling between adjacent spans.

Fixed tension system: Wire tension $T$ is treated as constant, with thermal expansion effects handled by adjusting $T$ manually.

Linear elasticity: Wire displacements are assumed to be small, enabling linear PDE formulation and excluding geometric nonlinearity.

Uniform properties: The wire's mass per unit length, cross-sectional area, and damping coefficient are constant along the span.

No external disturbances: Wind, track vibrations, and aerodynamic effects are neglected to focus on pantograph-induced dynamics.

**Numerical Modeling Assumptions**
Central finite difference discretization is used for spatial derivatives.

Newmark-β method with $\beta = \frac{1}{4}$ and $\gamma = \frac{1}{2}$ is used for time integration.

Pantograph force is modeled as a moving point load of constant magnitude $P_0$, without accounting for head compliance or force variation.

Initial conditions assume the wire is at rest with zero displacement and zero velocity.

These assumptions provide a streamlined foundation for exploring how train speed, wire tension, and damping affect dynamic performance and critical speed thresholds.

## Technologies
- Python 3
- NumPy
- Matplotlib
- SciPy

## Simulations Included
- Vertical Displacement at Midspan vs. Time
- Maximum Catenary Displacement vs. Temperature
- Estimated Critical Speed vs. Number of Droppers

## Results
- Midspan displacement peaks near critical speed, where the pantograph’s excitation frequency matches the natural frequency of the catenary wire.
- Rising ambient temperature increases vertical displacement due to reduced wire tension and stiffness, increasing the risk of contact loss.
- Increasing dropper quantity raises critical speed, improving dynamic stability by distributing loads and stiffening the wire.
- Supercritical speeds lead to high-frequency oscillations, which, while lower in amplitude, may accelerate mechanical fatigue.
- Temperature and structural effects compound: warmer conditions combined with sparse droppers significantly reduce safe operating margins.
- Each result is supported by plots showing displacement, contact gap, and system response under varying conditions.

