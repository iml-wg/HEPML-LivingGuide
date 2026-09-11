# Benchmarks & datasets

Shared datasets are what make claims in this field comparable. Listed here are the
ones used widely enough that a new method is expected to report on them. Datasets
tied to a single topic are listed in that section instead.

## Jet tagging & representations

- **JetClass**, Qu, Li, Qian ([arXiv:2202.03772](https://arxiv.org/abs/2202.03772)) —
  a large-scale jet tagging dataset released with Particle Transformer; now the
  default benchmark for architecture comparisons.
- **Aspen Open Jets**, Amram et al. ([arXiv:2412.10504](https://arxiv.org/abs/2412.10504)) —
  jets built from CMS Open Data, assembled for pre-training foundation models.
- **RODEM Jet Datasets**, Zoch et al.
  ([arXiv:2408.11616](https://arxiv.org/abs/2408.11616)) — jet datasets aimed at
  method development and comparison.

## Anomaly detection

- **LHC Olympics 2020**, Kasieczka et al.
  ([arXiv:2101.08320](https://arxiv.org/abs/2101.08320)) — R&D and black-box
  datasets, with a summary paper comparing many submitted methods.
- **Dark Machines Anomaly Score Challenge**, Aarrestad et al.
  ([arXiv:2105.14027](https://arxiv.org/abs/2105.14027)) — complementary in signals
  and event representation.
- **40 MHz unsupervised new-physics dataset**, Govorkova et al.
  ([arXiv:2107.02157](https://arxiv.org/abs/2107.02157)) — poses the problem under
  trigger-level constraints.

## Simulation

- **CaloChallenge 2022**, Krause et al.
  ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — three calorimeter
  datasets of increasing granularity, with agreed metrics; the reference benchmark
  for generative surrogates.
- **step2point**, Zaborowska et al.
  ([arXiv:2509.22340](https://arxiv.org/abs/2509.22340)) — detailed shower
  simulation for data-representation studies.
- **ColliderML**, Elitez et al.
  ([arXiv:2512.15230](https://arxiv.org/abs/2512.15230)) — an OpenDataDetector
  dataset at HL-LHC scale.

## Uncertainty & inference

- **FAIR Universe HiggsML Uncertainty Challenge**, Bhimji et al.
  ([arXiv:2410.02867](https://arxiv.org/abs/2410.02867)) — poses systematic-aware
  inference as a competition task.

## Deployment

- **wa-hls4ml**, Hawks et al.
  ([arXiv:2511.05615](https://arxiv.org/abs/2511.05615)) — benchmark and surrogate
  models for predicting FPGA resource use and latency.

!!! note
    This page is curated, not exhaustive. If a dataset has become a standard
    reference point in your subfield, please propose it via a
    [pull request](../contribute.md).
