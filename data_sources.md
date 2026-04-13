# Data Sources — Nuclear Power Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (Nuclear Power: Persistence Floor) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_environmental_damage`

$21.6B/yr; Chernobyl+Fukushima+Hanford $1.29T annualized

*Full citations: paper §4 (available SSRN).*

### `C2_health_externality`

$12B/yr; 1 of 28 nations built repository (Onkalo, Finland)

*Full citations: paper §4 (available SSRN).*

### `C3_climate_cost`

$20B/yr; 440 reactors, 9 weapon states, IAEA $180M budget

*Full citations: paper §4 (available SSRN).*

### `C4_ecosystem_degradation`

$15B/yr; systematic cost overruns, 5% of payoff, 34% of cost

*Full citations: paper §4 (available SSRN).*

### `C5_governance_capture`

$3B/yr; Price-Anderson caps at $16.3B vs $200B+ Fukushima

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $44.0B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *Nuclear Power (Persistence Floor)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
