# Generative models

## Overview

A generative model learns to draw samples from a distribution given examples. In
particle physics the distribution is usually one a simulator can already sample from,
just far too slowly.

Training data are effectively unlimited, but usually numerically expensive. The target is known to be physical. Success
can be measured against physics observables rather than judged by eye. And, unlike in
most domains, a *tractable likelihood* is often worth more than sample quality: it
makes evaluation quantitative, and it connects generation directly to density
estimation for searches and to likelihood-ratio inference. That is why normalizing
flows had a much larger impact here than their standing in the wider machine-learning
literature would suggest.

The architectural history runs adversarial models, variational autoencoders,
normalizing flows, and then diffusion, score-based, and conditional flow matching-based models, with transformers and
autoregressive approaches cutting across. Each transition was driven at least as much
by trainability and evaluability as by fidelity: GANs produced good samples but were
unstable and gave no likelihood, flows gave likelihoods at an architectural cost,
diffusion gave quality and stability but is slow to sample, and conditional flow matching simplified the training objective for high-fidelity samples.

## Recommended starting points

- **Generative Networks for LHC events**, Butter et al. (2020) ([arXiv:2008.08558](https://arxiv.org/abs/2008.08558)) — *generative networks for LHC events; the review closest to this section's scope*
- **Modern Machine Learning for LHC Physicists**, Plehn et al. (2022) ([arXiv:2211.01421](https://arxiv.org/abs/2211.01421)) — *lecture notes covering the architectures and their use across LHC physics*
- **Deep Generative Models for Detector Signature Simulation: An Analytical Taxonomy**, Hashemi et al. (2023) ([arXiv:2312.09597](https://arxiv.org/abs/2312.09597)) — *an analytical taxonomy of generative models for detector signatures — read this to organize the zoo before reading into it*
- **CaloChallenge 2022: A Community Challenge for Fast Calorimeter Simulation**, Krause et al. (2024) ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — *the CaloChallenge, effectively a controlled bake-off of architectures on one shared physics task*


## Curated paper list

*Foundational and representative work, grouped thematically. Not exhaustive by design — see [How to use this guide](../how-to-use.md).*

### Adversarial models

- **Learning Particle Physics by Example: Location-Aware Generative Adversarial Networks for Physics Synthesis**, de Oliveira et al. (2017) ([arXiv:1701.05927](https://arxiv.org/abs/1701.05927)) — *the first physics-aware GAN for calorimeter images, and the origin of the area*
- **CaloGAN: Simulating 3D high energy particle showers in multilayer electromagnetic calorimeters with generative adversarial networks**, Paganini et al. (2018) ([arXiv:1712.10321](https://arxiv.org/abs/1712.10321)) — *CaloGAN, which made three-dimensional shower generation a standard benchmark*
- **How to GAN Event Unweighting**, Backes et al. (2020) ([arXiv:2012.07873](https://arxiv.org/abs/2012.07873)) — *GAN-based event unweighting — a case where the model accelerates an exact procedure rather than replacing it*

### Variational autoencoders

- **DeepRICH: Learning Deeply Cherenkov Detectors**, Fanelli et al. (2019) ([arXiv:1911.11717](https://arxiv.org/abs/1911.11717)) — *DeepRICH: a learned model of a Cherenkov detector, an early demonstration outside calorimetry*
- **Variational Autoencoders for Jet Simulation**, Dohi (2020) ([arXiv:2009.04842](https://arxiv.org/abs/2009.04842)) — *variational autoencoders for jet simulation*

### Normalizing flows

- **Flow-based generative models for Markov chain Monte Carlo in lattice field theory**, Albergo et al. (2019) ([arXiv:1904.12072](https://arxiv.org/abs/1904.12072)) — *flows for lattice field theory, where combining a flow with an accept/reject step gives asymptotically exact sampling*
- **i-flow: High-Dimensional Integration and Sampling with Normalizing Flows**, Gao et al. (2020) ([arXiv:2001.05486](https://arxiv.org/abs/2001.05486)) — *i-flow: flows for high-dimensional numerical integration and sampling, the same machinery used for a different purpose*
- **Measuring QCD Splittings with Invertible Networks**, Bieringer et al.  (2020) ([arXiv:2012.09873](https://arxiv.org/abs/2012.09873)) — *invertible networks applied to measuring QCD splittings, illustrating the inference side of tractable likelihoods*
- **CaloFlow: Fast and Accurate Generation of Calorimeter Showers with Normalizing Flows**, Krause et al. (2021) ([arXiv:2106.05285](https://arxiv.org/abs/2106.05285)) — *CaloFlow: the first application of normalizing flows to detector simulation and the first to fool a classifier test*

### Diffusion and score-based models

- **Score-based Generative Models for Calorimeter Shower Simulation**, Mikuni et al. (2022) ([arXiv:2206.11898](https://arxiv.org/abs/2206.11898)) — *score-based generation for calorimeter showers; now the dominant approach in detector simulation*
- **Jet Diffusion versus JetGPT -- Modern Networks for the LHC**, Butter et al. (2023) ([arXiv:2305.10475](https://arxiv.org/abs/2305.10475)) — *a direct comparison of diffusion against an autoregressive transformer on the same LHC task*
- **CaloDREAM – Detector response emulation via attentive flow matching**, Favaro et al. (2024) ([arXiv:2405.09629](https://arxiv.org/abs/2405.09629)) — *conditional flow matching with transformer elements. *

### Transformers and autoregressive models

- **Phase Space Sampling and Inference from Weighted Events with Autoregressive Flows**, Verheyen et al. (2020) ([arXiv:2011.13445](https://arxiv.org/abs/2011.13445)) — *autoregressive models for phase-space sampling and inference from weighted events*
- **Learning the language of QCD jets with transformers**, Finke et al. (2023) ([arXiv:2303.07364](https://arxiv.org/abs/2303.07364)) — *treating jet constituents as a language, the clearest statement of the sequence-modeling analogy*

### Evaluation

- **Understanding Event-Generation Networks via Uncertainties**, Bellagente et al. (2021) ([arXiv:2104.04543](https://arxiv.org/abs/2104.04543)) — *using uncertainties to understand what an event-generation network has actually learned*
- **Evaluating generative models in high energy physics**, Kansal et al. (2023) ([arXiv:2211.10295](https://arxiv.org/abs/2211.10295)) — *on evaluating generative models in high energy physics; the metrics problem stated directly*
- **How to Understand Limitations of Generative Networks**, Das et al. (2023) ([arXiv:2305.16774](https://arxiv.org/abs/2305.16774)) — *on the limitations of generative networks — what they can and cannot be expected to reproduce*
- **Generative Models and Statistical Validation**, Diefenbacher et al. (2026) ([arXiv:2605.30453](https://arxiv.org/abs/2605.30453)) — *statistical validation of generative models*

## Benchmarks, datasets & software

- **CaloChallenge 2022: A Community Challenge for Fast Calorimeter Simulation**, Krause et al. (2024) ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — *CaloChallenge 2022 datasets and metrics, the standard comparison point for detector surrogates*
- **LEMURS dataset: Large-scale multi-detector ElectroMagnetic Universal Representation of Showers**, McKeown et al. (2025) ([arXiv:2509.05108](https://arxiv.org/abs/2509.05108)) — *LEMURS: large-scale multi-detector electromagnetic shower data*
- **JetClass: A Large-Scale Dataset for Deep Learning in Jet Physics**, Qu et al. (2022) ([arXiv:2202.03772](https://arxiv.org/abs/2202.03772)) — *One of the largest jet datasets, was initially used to train the Particle Transformer for Jet Tagging*

## Open questions

Evaluation is the open question that shapes everything else. No agreed metric
establishes that a surrogate is safe for a specific measurement, correlated errors
can hide behind good marginals, and the community has been moving from
distributional metrics toward downstream physics benchmarks precisely because of it.

Attaching an uncertainty to a generated sample has been attempted — Bayesian and
ensemble treatments of generative networks exist — but no approach has become standard,
and it is not established that the resulting uncertainties are calibrated where it
matters. That is the prerequisite for using surrogates in precision measurements rather
than in studies. Behavior in the tails — usually where the physics is — is poorly characterized 
for every architecture here. And there is a live question about how much physics structure
should be built into a generative architecture versus learned, which is the same
argument playing out in [equivariant architectures](equivariant-geometric.md) and
[foundation models](foundation-models.md).

## Further reading

*Relevant work that is not an entry point — too specialized, too recent, or simply not where a newcomer should start. Suggestions that do not fit the curated list above belong here rather than being turned away.*

- **Systematic Evaluation of Generative Machine Learning Capability to Simulate Distributions of Observables at the Large Hadron Collider**, Gavranovivc et al. (2023) ([arXiv:2310.08994](https://arxiv.org/abs/2310.08994)) — *a systematic evaluation of generative capability, longer and more specialized than the entries above*

## Cross-references

- Detector and event-generation applications are under [Simulation & fast emulation](../applications/simulation.md).
- Density estimation for searches is under [Anomaly detection](../applications/anomaly-detection.md).
- Exact sampling for gauge theory is under [Lattice field theory](../applications/lattice.md).
- Likelihood-ratio inference is under [Density estimation & likelihood ratios](density-ratio.md).
