# investor-information-diffusion
Python simulation exploring how investor network structure and sharing frequency affect information diffusion.
# Information Diffusion Across Investor Networks

A reproducible Python simulation exploring how investor network
structure and sharing frequency affect the speed and reach of
information diffusion.

## Research question

How do connections between investors and their probability of sharing
information affect how quickly financial news spreads?

## Method

The model contains 100 investors and 200 undirected connections.
Five randomly selected investors initially know the information.

Each round, informed investors can contact one randomly selected
neighbour with a specified sharing probability. Newly informed
investors begin sharing in the following round.

Networks are generated using the Watts–Strogatz model. Rewiring
changes a regular ring into networks containing connections between
distant parts of the original ring.

The main experiment compares six rewiring probabilities, with
200 diffusion runs per setting. A sensitivity analysis tests three
sharing probabilities across three network settings.

## Main results

At a 50% sharing probability:

| Rewiring probability | Average informed after 30 rounds | Runs reaching 90% coverage |
|---|---:|---:|
| 0% | 77.4 | 22% |
| 5% | 93.1 | 74.5% |
| 10% | 97.2 | 95% |
| 25% | 99.6 | 100% |
| 50% | 99.6 | 100% |
| 100% | 99.6 | 100% |

Introducing 10% rewiring increased average coverage by 19.8
percentage points compared with the ring.

Further rewiring produced smaller gains in final coverage.
Similar final coverage did not imply identical diffusion speeds:
average time to 90% coverage was 19.2 rounds at 25% rewiring,
17.7 at 50%, and 17.8 at 100%.

The sensitivity analysis found greater average coverage in rewired
networks at all tested sharing probabilities. However, shortcuts
did not guarantee widespread diffusion when sharing was infrequent.

## How to run

Open `information_diffusion.ipynb` in Google Colab and run all cells
from top to bottom. Alternatively, use Jupyter with these libraries:

- NumPy
- NetworkX
- Matplotlib

Explicit seeds control network generation and diffusion randomness.

## Limitations

This is a stylised simulation, not an empirical model of financial
markets. It does not model trading, prices or investment returns.

Investors have identical sharing probabilities, always accept the
information and never forget it. Networks remain fixed within runs.

Rewiring changes several network properties simultaneously.
Runs sharing a generated network are not independent network
observations. Time-to-threshold averages exclude runs that do not
reach the threshold within 30 rounds.

## Files

- `information_diffusion.ipynb` — model, checks, experiments,
  charts and interpretation.

## Author

Mitchell Fletcher
BA Economics, Lancaster University
