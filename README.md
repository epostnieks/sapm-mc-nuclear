# SAPM Monte Carlo — Nuclear Power / Persistence Floor

**Public replication repository for quantitative results in:**

> Postnieks, E. (2026). *Nuclear Power (Persistence Floor).* SAPM Working Paper. SSRN.

This repository provides everything needed to independently reproduce, audit,
and extend the Monte Carlo simulation underlying the paper's core results.
The paper is available on SSRN.

---

## Results (N = 100,000 draws, seed = 42)

| Statistic | Value |
|-----------|-------|
| **β_W median** | **0.54** |
| β_W mean | 0.55 |
| β_W std | 0.11 |
| **90% CI** | **[0.4, 0.7]** |
| 99% CI | [0.3, 0.9] |
| P(β_W < 1) | 99.9090% |
| **ΔW median** | **$23.7B/yr** |
| Π (revenue) | $44.0B/yr |

**β_W = 0.54** means the nuclear power industry destroys **$0.54 in system
welfare for every $1.00 in revenue** — across 5 channels and 100,000 Monte Carlo draws.

**Classification**: Class 3 — Troublesome

---

## What Is β_W?

```
β_W = ΔW / Π
```

- **ΔW** = total annualized welfare destruction ($B/yr) across all channels
- **Π** = annual industry **revenue** ($B/yr) — not profit

β_W > 1: industry destroys more welfare than it captures in revenue.
β_W > 3: Strong Intractability threshold — reform requires structural replacement.

---

## Quick Start

```bash
git clone https://github.com/epostnieks/sapm-mc-nuclear.git
cd sapm-mc-nuclear
pip install numpy scipy
python mc_simulation.py
```

Expected output: `β_W median : 0.54` and `ΔW median : $23.7B/yr`

---

## Welfare Channels

| Channel | Median ($B/yr) | 90% CI | Distribution |
|---------|---------------|--------|--------------|
| C1_environmental_damage | $9.3B | [$5.6B, $15.2B] | Lognormal |
| C2_health_externality | $5.8B | [$3.5B, $9.6B] | Lognormal |
| C3_climate_cost | $4.7B | [$3.8B, $5.6B] | Normal |
| C4_ecosystem_degradation | $2.3B | [$1.4B, $3.8B] | Lognormal |
| C5_governance_capture | $1.2B | [$0.7B, $2.0B] | Lognormal |
| **Total ΔW** | **$23.7B** | **[$17.3B, $32.8B]** | Correlated (ρ=0.3) |

---

## Impossibility Floor

The floor β_W ≥ 0.3 cannot be breached by any policy while the
industry continues to operate. In 100,000 draws, only **0.0680%**
fall below this floor — confirming the structural constraint.

## Repository Contents

| File | Description |
|------|-------------|
| `mc_simulation.py` | Self-contained simulation — no private pipeline imports |
| `mc_results.json` | Pre-run results (100K draws, seed=42) — matches paper |
| `mc_histogram.json` | Binned β_W distribution (80 bins) for companion chart |
| `assumptions.md` | Every parameter: value, derivation, source |
| `data_sources.md` | Full citation list for all empirical inputs |

---

## Replication Notes

Results are seeded and deterministic. Tested with:
```
numpy==1.26.4  scipy==1.12.0  Python 3.11.9
```

The `median` and `ci_90` (to 1 decimal) match exactly across compatible versions.

---

## License

CC BY 4.0. Cite as:

> Postnieks, E. (2026). *SAPM Monte Carlo — Nuclear Power (Persistence Floor)*.
> GitHub: epostnieks/sapm-mc-nuclear.
> https://github.com/epostnieks/sapm-mc-nuclear
