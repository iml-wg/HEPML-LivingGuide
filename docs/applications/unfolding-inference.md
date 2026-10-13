# Unfolding & simulation-based inference

## Overview

Particle physics has excellent simulators and no tractable likelihood. Everything in
this section follows from that. Traditional analysis bridges the gap by binning a small
number of summary statistics, which is statistically lossy and forces the analyst to
decide in advance what to summarize. Simulation-based inference — also called
likelihood-free inference — instead uses machine learning to construct the likelihood,
the likelihood ratio, or the posterior directly from simulated samples.

Unfolding is the same problem viewed from the other end. 
Instead of inferring latent parameters for a given observation, 
it infers an entire latent distribution from the observed data. 
It can be used, for example, to correct for detector distortions 
so that a measurement can be compared with theoretical predictions, 
or reused years later to test theories that did not exist when 
the data were taken. Classical unfolding methods typically invert 
a detector response matrix, while learned methods can perform 
unfolding unbinned and simultaneously in many dimensions. 
ML-based unfolding methods can be roughly divided into 
classifier-based or generator-based methods.

The particle-physics contribution to this cross-disciplinary field is distinctive.
Because the simulator's internals are accessible, quantities such as the joint
likelihood ratio of the latent process can be extracted and used as training targets —
"mining gold" — giving sample efficiency far beyond what a black-box simulator would
allow. That is why methods developed here are of interest well outside the field.

Not all inference in HEP is simulation-based. Weakly supervised searches infer a signal
from data alone, without trusting a simulation to model the background, which lives
under [Anomaly detection](anomaly-detection.md).

## Recommended starting points

- **The frontier of simulation-based inference**, Cranmer et al. (2019) ([arXiv:1911.01429](https://arxiv.org/abs/1911.01429)) — *the standard cross-disciplinary review of simulation-based inference; the single best entry point*
- **Simulation-based inference methods for particle physics**, Brehmer et al. (2020) ([arXiv:2010.06439](https://arxiv.org/abs/2010.06439)) — *the particle-physics-specific treatment, closer to how these methods are actually deployed*
- **The Landscape of Unfolding with Machine Learning**, Huetsch et al. (2024) ([arXiv:2404.18807](https://arxiv.org/abs/2404.18807)) — *a survey of ML unfolding methods and how they relate to each other*
- **A Practical Guide to Unbinned Unfolding**, Canelli et al. (2025) ([arXiv:2507.09582](https://arxiv.org/abs/2507.09582)) — *a practical guide to unbinned unfolding, closer to implementation than the surveys*
- **simulation-based-inference.org** ([website](https://simulation-based-inference.org)) — *a living cross-disciplinary guide to SBI maintained outside HEP, with a searchable bibliography; the best place to see how the methods here connect to cosmology, neuroscience and epidemiology.*
- **An Introduction to Bayesian and Frequentist Simulation-Based Inference with Machine Learning**, Dax et al. (2026) ([arXiv:2607.21702](https://arxiv.org/abs/2607.21702)) - *a tutorial-style introduction to using machine learning for simulation-based inference, explaining how neural methods can do parameter and distribution-level estimation in Bayesian and frequentist frameworks*

## Curated paper list
### NSBI
- **Approximating Likelihood Ratios with Calibrated Discriminative Classifiers**, Cranmer et al. (2015) ([arXiv:1506.02169](https://arxiv.org/abs/1506.02169)) — *the foundational result that a calibrated classifier approximates the likelihood ratio — the idea nearly everything else here rests on*
- **Constraining Effective Field Theories with Machine Learning**, Brehmer et al. (2018) ([arXiv:1805.00013](https://arxiv.org/abs/1805.00013)) — *mining gold: exploiting simulator internals to make likelihood-ratio estimation dramatically more sample-efficient*
- **MadMiner: Machine learning-based inference for particle physics**, Brehmer et al. (2020) ([arXiv:1907.10621](https://arxiv.org/abs/1907.10621)) — *MadMiner, the reference implementation for collider EFT inference*
### Discriminative Unfolding
- **OmniFold: A Method to Simultaneously Unfold All Observables**, Andreassen et al. (2020) ([arXiv:1911.09107](https://arxiv.org/abs/1911.09107)) — *OmniFold: iterative, unbinned, simultaneously multi-dimensional unfolding by reweighting; the method most experiments have adopted*
- **A simultaneous unbinned differential cross section measurement of twenty-four Z+jets kinematic observables with the ATLAS detector**, The ATLAS Collaboration (2024) ([arXiv:2405.20041](https://arxiv.org/pdf/2405.20041)) - *First experimental unfolding LHC-analysis using OmniFold inside ATLAS*
- **Machine Learning-based Unfolding for Cross Section Measurements in the Presence of Nuisance Parameters**, Zhu et al. (2025) ([arXiv:2512.07074](https://arxiv.org/pdf/2512.07074)) - *Machinery to treat nuisance parameters within an OmniFold reweighting setting*
- **Unfolding without Iterations, Adversaries, or Surrogates**, Ore and Plehn (2026) ([arXiv:2602.24282](https://arxiv.org/pdf/2602.24282)) - *AUSSIE: OmniFold-like reweighting method without iterations*
- **Reweighting Adversarial Networks for Unbinned Unfolding**, Qureshi et al. (2026) ([arXiv:2606.06603](https://arxiv.org/pdf/2606.06603)) - *OmniFold-like reweighting method with additional adversarial network*

### Generative Unfolding
- **Invertible Networks or Partons to Detector and Back Again**, Bellagente et al. (2020) ([arXiv:2006.06685](https://arxiv.org/abs/2006.06685)) — *conditional invertible networks learn the parton-level distribution conditioned on the detector-level event, so unfolding becomes sampling from a per-event posterior over parton-level configurations rather than a single point estimate*
- **An unfolding method based on conditional invertible neural networks (cINN) using iterative training**, Backes et al. (2022) ([arXiv:2212.08674](https://arxiv.org/pdf/2212.08674)) - *conditional invertible networks learn the posterior distribution and reduce bias by iterations*
- **Generative unfolding with distribution mapping**, Butter et al. (2024) ([arXiv:2411.02495](https://arxiv.org/pdf/2411.02495)) - *Bridge-based unfolding methods that directly morph detector-level measurements into particle-level distributions.*
- **Simulation-Prior Independent Neural Unfolding Procedure**, Butter et al. (2025) ([arXiv:2507.15084](https://arxiv.org/pdf/2507.15084)) - *SPINUP: Minimizing forward convolution to match measurement w.r.t. particle-level distribution by three different generative networks, no iterations needed*
- **Analysis-Ready Generative Unfolding**, Butter et al. (2025) ([arXiv:2509.02708](https://arxiv.org/pdf/2509.02708)) - *Generative unfolding in the presence of background, efficiency and acceptance effects*
- **Generative Unfolding of Jets and Their Substructure**, Petitjean et al. (2025) ([arXiv:2510.19906](https://arxiv.org/pdf/2510.19906)) - *Generative unfolding in high dimensions*
## Benchmarks, datasets & software

- **OmniFold: A Method to Simultaneously Unfold All Observables**, Andreassen et al. (2020) ([arXiv:1911.09107](https://arxiv.org/abs/1911.09107)) - *simulated Z+jets events available [here](https://zenodo.org/records/3548091)*
- **Large version of the OmniFold dataset**, Nachman and Mikuni (2024) - *containing more Z+jets events available [here](https://doi.org/10.5281/zenodo.10668638)*

## Open questions

*How can we propagate uncertainties through the unfolding, statistical as well as systematics? How to deal with different forward maps coming from summary statistics, currently it's a systematic uncertainty. How to trust our unfolded results. How to treat nuisance parameters for generative methods.*

## Further reading

*Relevant work that is not an entry point — too specialized, too recent, or simply not where a newcomer should start. Suggestions that do not fit the curated list above belong here rather than being turned away.*

*Nothing listed yet.*

## Cross-references

- The shared machinery is under [Density estimation & likelihood ratios](../methods/density-ratio.md).
- Inference without a trusted simulator is under [Anomaly detection](anomaly-detection.md).
- Systematics and coverage are under [Uncertainty quantification](../methods/uncertainty.md).
- Gradients through the simulator are under [Differentiable programming](../methods/differentiable.md).
