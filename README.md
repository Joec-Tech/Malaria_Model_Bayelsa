# Compartmental Modelling for Malaria in Brass LGA

This repository contains a compartmental model for simulating and analyzing malaria incidence in Brass LGA, Bayelsa State, Nigeria.

## Project Objectives
This project aims to:
1. Develop a mathematical model of malaria transmission.
2. Solve the model using numerical techniques.
3. Fit the model to real-world malaria incidence data.
4. Provide clear descriptions of the model compartments and parameters.

## Model Equation

The dynamics of the human and mosquito populations are governed by the following system of differential equations:

$$
\frac{dS_h}{dt} = \Lambda_h - \frac{\beta_h S_h I_m}{N_m} + \alpha_h R_h
$$

$$
\frac{dI_h}{dt} = \frac{\beta_h S_h I_m}{N_m} - \gamma_h I_h
$$

$$
\frac{dR_h}{dt} = \gamma_h I_h - \alpha_h R_h
$$

$$
\frac{dS_m}{dt} = \Lambda_m - \frac{\beta_m S_m I_h}{N_h} - \mu_m S_m
$$

$$
\frac{dI_m}{dt} = \frac{\beta_m S_m I_h}{N_h} - \mu_m I_m
$$

##  Model Description

The model is a compartmental SIR-based model with two interacting populations: humans and mosquitoes.

### Human Compartments:
- $S_h$: Susceptible humans  
- `I_h`: Infected humans  
- `R_h`: Recovered humans  

### Mosquito Compartments:
- `S_m`: Susceptible mosquitoes  
- `I_m`: Infected mosquitoes  

### Incidence:
- `Inc`: Cumulative incidence in humans

##  Assumptions

- Human lifespan is long; human mortality is neglected.
- Malaria-related human deaths are negligible.
- Mosquito-to-human population ratio is 200:1.
- Equal initial infection proportion in both populations.
- Mosquito population remains constant.


##  Time Unit
- The unit of time used in the simulation is 1 month (30 days).
## Parameter Classification

- **Known parameters** (from demographic or biological assumptions):
  - `μ_m`, `λ_m`, `λ_h`, `γ_h`

- **Unknown parameters** (estimated via curve fitting):
  - `β_h`, `α_h`, `β_m`

##  Files in This Repository

- `Data.txt`: Input incidence data
- `malaria_model.py` or `.ipynb`: Model implementation and fitting
- `README.md`: Project overview (this file)

##  Tools & Libraries

- Python with:
  - `numpy`
  - `scipy.integrate` for solving ODEs
  - `scipy.optimize.curve_fit` for parameter estimation
  - `matplotlib` for plotting results

## Results Snapshot

Final fitted parameter values:

| Parameter | Estimate | 95% CI Lower | 95% CI Upper |
|-----------|----------|--------------|--------------|
| β_h       | 0.3793   | 0.2609       | 0.4976       |
| β_m       | 5.9559   | 3.9608       | 7.9511       |
| α_h       | 3.4479   | 2.4222       | 4.4736       |

## Contact

For questions or feedback, feel free to open an issue or reach out.

emenikecharles2@gmail.com for quick response.


