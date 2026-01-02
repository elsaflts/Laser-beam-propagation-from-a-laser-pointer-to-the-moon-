# Laser Beam Propagation from Earth to the Moon

**PHY204 – Electromagnetic Waves Project**

This project studies how a laser beam emitted from Earth propagates to the Moon under idealized conditions. Using analytical modeling and numerical simulations, we investigate beam divergence, intensity loss, and the influence of beam shaping over astronomical distances (~384,400 km).

The work combines classical electromagnetic theory with numerical methods to understand the physical limits of long-distance laser transmission.

---

## Project Objectives

- Derive the **paraxial wave equation** from Maxwell’s equations
- Model laser beam propagation over Earth–Moon distances
- Compare **Gaussian**, **Super-Gaussian**, square, and noisy beam envelopes
- Identify which physical parameters maximize intensity on the Moon
- Evaluate feasibility for real-world applications (ranging, communication, power delivery)

---

## Physical Model

- Monochromatic laser beam
- Paraxial (small-angle) approximation
- Clear atmosphere, vacuum propagation
- No absorption, scattering, or turbulence
- Cylindrical symmetry

The electric field envelope satisfies the paraxial wave equation:

\[
\nabla_\perp^2 E + 2 i k_0 \frac{\partial E}{\partial z} = 0
\]

---

## Numerical Methods

Two numerical propagation schemes were implemented and compared:

### 1. Split-Step Fourier Method (FFT)
- Spectral accuracy for diffraction
- Efficient \(O(N \log N)\) complexity
- Uses an adaptive propagation window
- Found to be sensitive to normalization and long-distance accumulation errors

### 2. Crank–Nicolson Method (Final Model)
- Second-order accurate and unconditionally stable
- Implemented in **computational space**
- Uses cylindrical coordinates
- Includes edge absorption to suppress reflections
- Produces excellent agreement with analytical solutions up to lunar distance

The Crank–Nicolson method in computational space is the **primary and validated solver** used for final results.

---

## Beam Envelopes Studied

- **Gaussian beams**
- **Super-Gaussian beams** (orders \(n = 2\) to \(n > 8\))
- **Square (top-hat) beams**
- **Noisy Gaussian beams** (to mimic imperfections)

---

## Key Results

### Diffraction Dominates
- Beam divergence is the main limitation, not laser power
- A typical laser pointer spreads to **hundreds of kilometers** at the Moon

### Parameter Sensitivity
- Spot size on the Moon scales **linearly with wavelength**
- Larger beam waist significantly reduces divergence
- Power scales intensity but **does not affect beam geometry**

### Beam Shaping
- Square beams suffer strong diffraction and sidelobes
- Super-Gaussian beams provide improved confinement
- Optimal Super-Gaussian order exists (too high worsens divergence)
- Noisy beams self-regularize through diffraction

### Power Estimates (Order of Magnitude)
| Application | Target Intensity | Required Power |
|------------|------------------|----------------|
| Lunar Laser Ranging | \(1\,\mu W/m^2\) | ~60 W |
| Lunar Communication | \(1\,mW/m^2\) | ~60 kW |
| Surface Heating | \(1\,kW/m^2\) | ~60 MW |

Only **laser ranging** is comfortably feasible with current technology.

---

## Conclusions

- A laser beam can indeed propagate from Earth to the Moon
- Diffraction fundamentally limits power delivery
- Beam waist and envelope shape are critical optimization parameters
- Crank–Nicolson in computational space provides a robust framework for astronomical-scale simulations
- Real-world effects (atmospheric turbulence, absorption, misalignment) would significantly reduce efficiency

---

## Authors

- Victoria Amgoune  
- Yasmine Nourlil  
- Elsa Felts  
- Timothey Szczepanski  

---

## References

- N. Hansen et al., *COCO Platform*
- A. Couairon, *Laser Pulse Propagation Models*
- PHY204 Lecture Notes

---

## Report

The full project report (derivations, algorithms, figures, and results) is available in:

