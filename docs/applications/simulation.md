# Simulation & fast emulation

## Overview

Simulation is what turns a theory into something comparable with data, and in
collider physics it is the dominant computational cost. The chain runs from the
scattering amplitude, through integration over phase space, through parton shower and
hadronization, to the detector response — and every link in it is expensive enough
that someone has tried to replace it with a learned surrogate.

This section covers the whole chain. That is a deliberate choice: the stages have very
different physics but a common structure, in that each replaces an expensive
deterministic or stochastic evaluation with a model trained on its output. The same
architectures move between them, and so do the failure modes.

The problem is unusually well posed for machine learning. Training data are effectively
unlimited, since the simulator can be run to generate more, the target is known to be
physical, and success can be judged against physics observables rather than perceptual
quality. What makes it hard is not fitting the distribution but knowing when the fit is
good enough, since a surrogate that matches every marginal can still bias a precision
measurement through a correlation it never learned. That question, rather than any
particular architecture, is what the field has spent its effort on.

Two threads are worth separating as you read. Surrogates that *replace* a calculation
must be accurate to the precision of the measurement downstream. Surrogates used as
*proposals* — importance-sampling maps, unweighting helpers — need only be good enough
to accelerate an exact procedure, because a correction step restores exactness. The
second class is far easier to trust, and that asymmetry explains much of what has been
adopted in production versus what remains a demonstration.

## Recommended starting points

- **A survey of machine learning-based physics event generation**, Alanazi et al. (2021) ([arXiv:2106.00643](https://arxiv.org/abs/2106.00643)) — *a survey of ML-based physics event generation, complementary in emphasis to the Snowmass report*
- **Machine Learning and LHC Event Generation**, Badger et al. (2022) ([arXiv:2203.07460](https://arxiv.org/abs/2203.07460)) — *the Snowmass report on ML for LHC event generation. The best entry point for the generation half of the chain*
- **Deep Generative Models for Detector Signature Simulation: An Analytical Taxonomy**, Hashemi et al. (2023) ([arXiv:2312.09597](https://arxiv.org/abs/2312.09597)) — *an analytical taxonomy of generative models for detector signatures, useful for organizing the architecture zoo*
- **CaloChallenge 2022: A Community Challenge for Fast Calorimeter Simulation**, Krause et al. (2024) ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — *the CaloChallenge: a controlled comparison of detector surrogates on shared data with agreed metrics*

## Curated paper list

*Foundational and representative work, grouped thematically. Not exhaustive by design — see [How to use this guide](../how-to-use.md).*

### Amplitudes and matrix elements

- **Using neural networks for efficient evaluation of high multiplicity scattering amplitudes**, Badger et al. (2020) ([arXiv:2002.07516](https://arxiv.org/abs/2002.07516)) — *among the first amplitude surrogates, and the one that set the agenda: at high multiplicity the evaluation cost grows factorially, and the network has to be right in the infrared regions where the amplitude diverges. Everything below is a response to that problem*
- **A factorisation-aware Matrix element emulator**, Maître et al. (2021) ([arXiv:2107.06625](https://arxiv.org/abs/2107.06625)) — *a factorisation-aware emulator: building the known singular structure into the model rather than making it learn QCD from scratch*
- **Loop Amplitudes from Precision Networks**, Badger et al. (2023) ([arXiv:2206.14831](https://arxiv.org/abs/2206.14831)) — *loop amplitudes from precision networks, pushing surrogates to the accuracy NLO calculations need*
- **Amplitude Uncertainties Everywhere All at Once**, Bahl et al. (2025) ([arXiv:2509.00155](https://arxiv.org/abs/2509.00155)) — *per-prediction uncertainty estimates for learned amplitudes, which is what turns a surrogate from fast into usable: it lets you decide point by point where the network can be trusted and where the exact calculation has to be called instead*
- **Amplitude Surrogates for Multi-Jet Processes**, Beccatini et al. (2025) ([arXiv:2512.11036](https://arxiv.org/abs/2512.11036)) — *puts the uncertainty estimates to work: the surrogate is invoked or bypassed according to its own predicted error, so the exact calculation is only called where it is actually needed*

### Phase-space sampling and integration

- **Efficient Monte Carlo Integration Using Boosted Decision Trees and Generative Deep Neural Networks**, Bendavid (2017) ([arXiv:1707.00028](https://arxiv.org/abs/1707.00028)) — *the pre-neural baseline using boosted decision trees, useful for seeing what the learned methods actually improved on*
- **Neural Network-Based Approach to Phase Space Integration**, Klimek et al. (2018) ([arXiv:1810.11509](https://arxiv.org/abs/1810.11509)) — *the first neural approach to phase-space integration, framing the problem as learning a change of variables*
- **Exploring phase space with Neural Importance Sampling**, Bothmann et al. (2020) ([arXiv:2001.05478](https://arxiv.org/abs/2001.05478)) — *neural importance sampling for phase space*
- **Event Generation with Normalizing Flows**, Gao et al. (2020) ([arXiv:2001.10028](https://arxiv.org/abs/2001.10028)) — *neural importance sampling for phase space, independentfrom, but simultaneously to Bothmann et al.*
- **MadNIS -- Neural Multi-Channel Importance Sampling**, Heimel et al. (2022) ([arXiv:2212.06172](https://arxiv.org/abs/2212.06172)) — *MadNIS: multi-channel importance sampling combining learned maps with the channel decomposition generators already use*

### Event generation and unweighting

- **Deep Learning as a Parton Shower**, Monk (2018) ([arXiv:1807.03685](https://arxiv.org/abs/1807.03685)) — *a parton shower expressed as a learned model, connecting generation to the structure of QCD emission*
- **DijetGAN: A Generative-Adversarial Network Approach for the Simulation of QCD Dijet Events at the LHC**, Di Sipio et al. (2019) ([arXiv:1903.02433](https://arxiv.org/abs/1903.02433)) — *one of the first attempts to generate full events rather than detector images, and a useful marker of where the field started on this problem*
- **How to GAN Event Unweighting**, Backes et al. (2020) ([arXiv:2012.07873](https://arxiv.org/abs/2012.07873)) — *unweighting with generative models, one of the clearest cases where a surrogate accelerates an exact procedure rather than replacing it*
- **Learning to Simulate High Energy Particle Collisions from Unlabeled Data**, Howard et al. (2021) ([arXiv:2101.08944](https://arxiv.org/abs/2101.08944)) — *OTUS: an optimal-transport approach that learns the latent-to-observed map from unlabeled data, so the simulator is trained against real events rather than against another simulator*
- **Unweighting multijet event generation using factorisation-aware neural networks**, Janssen et al. (2023) ([arXiv:2301.13562](https://arxiv.org/abs/2301.13562)) — *factorisation-aware unweighting for multijet generation, bringing physics structure to the same problem*

### Detector simulation

- **Learning Particle Physics by Example: Location-Aware Generative Adversarial Networks for Physics Synthesis**, de Oliveira et al. (2017) ([arXiv:1701.05927](https://arxiv.org/abs/1701.05927)) — *LAGAN: the first location-aware generative model for calorimeter images, and the paper that opened the area*
- **CaloGAN : Simulating 3D high energy particle showers in multilayer electromagnetic calorimeters with generative adversarial networks**, Paganini et al. (2018) ([arXiv:1712.10321](https://arxiv.org/abs/1712.10321)) — *CaloGAN: three-dimensional multi-layer showers, setting the problem template still in use*
- **CaloFlow: Fast and Accurate Generation of Calorimeter Showers with Normalizing Flows**, Krause et al. (2021) ([arXiv:2106.05285](https://arxiv.org/abs/2106.05285)) — *CaloFlow: tractable likelihoods for shower generation, first application of normalizing flows to detector simulation, good quality based on new classifier test*
- **Score-based Generative Models for Calorimeter Shower Simulation**, Mikuni et al. (2022) ([arXiv:2206.11898](https://arxiv.org/abs/2206.11898)) — *score-based diffusion for showers*
- **CaloDREAM – Detector response emulation via attentive flow matching**, Favaro et al. (2024) ([arXiv:2405.09629](https://arxiv.org/abs/2405.09629))— *conditional flow matching with transformer elements. *

### Evaluation and validation

- **Understanding Event-Generation Networks via Uncertainties**, Bellagente et al. (2021) ([arXiv:2104.04543](https://arxiv.org/abs/2104.04543)) — *understanding event-generation networks through their uncertainties, an early attempt to make a surrogate say when it does not know*
- **Evaluating generative models in high energy physics**, Kansal et al. (2023) ([arXiv:2211.10295](https://arxiv.org/abs/2211.10295)) — *on evaluating generative models in high energy physics — the metrics question posed directly*
- **How to Understand Limitations of Generative Networks**, Das et al. (2023) ([arXiv:2305.16774](https://arxiv.org/abs/2305.16774)) — *on the limitations of generative networks — what they can and cannot be expected to reproduce*
- **A First Full Physics Benchmark for Highly Granular Calorimeter Surrogates**, Buss et al. (2025) ([arXiv:2511.17293](https://arxiv.org/abs/2511.17293)) — *a full physics benchmark for calorimeter surrogates, measuring downstream impact rather than distributional agreement*
- **Generative Models and Statistical Validation**, Diefenbacher et al. (2026) ([arXiv:2605.30453](https://arxiv.org/abs/2605.30453)) — *statistical validation of generative models, an area the field arrived at late*

## Benchmarks, datasets & software

- **CaloChallenge 2022: A Community Challenge for Fast Calorimeter Simulation**, Krause et al. (2024) ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — *CaloChallenge 2022 datasets at three detector granularities, with agreed metrics*
- **LEMURS dataset: Large-scale multi-detector ElectroMagnetic Universal Representation of Showers**, McKeown et al. (2025) ([arXiv:2509.05108](https://arxiv.org/abs/2509.05108)) — *LEMURS: large-scale multi-detector electromagnetic shower data*
- **step2point dataset: Detailed shower simulation for data representation studies**, Zaborowska et al. (2025) ([arXiv:2509.22340](https://arxiv.org/abs/2509.22340)) — *step2point: detailed shower simulation for data-representation studies*
- **ColliderML: The First Release of an OpenDataDetector High-Luminosity Physics Benchmark Dataset**, Elitez et al. (2025) ([arXiv:2512.15230](https://arxiv.org/abs/2512.15230)) — *ColliderML: an OpenDataDetector dataset at HL-LHC scale*

## Open questions

How good is good enough is still unsettled, and it is a question about downstream
analyses rather than about generative modeling. Metrics are correspondingly
contested, which is why the field has been shifting from distributional measures
toward full physics benchmarks.

For the generation stages the sharper question is whether learned surrogates can reach
the precision that NLO and NNLO calculations demand, and how to certify that they have.
Amplitude surrogates are furthest along: per-prediction uncertainty estimates now
exist, and can be used to decide where the network is trustworthy and where the exact
calculation must be called instead. What remains open is whether those uncertainties
are themselves reliable across the full phase space, particularly in the sparsely
sampled regions where the surrogate is least constrained, and how to propagate them
into a cross section.

Generalisation beyond the training phase space and behavior in the rare tails that
often carry the physics are open across the whole chain.

## Further reading

*Relevant work that is not an entry point — too specialized, too recent, or simply not where a newcomer should start. Suggestions that do not fit the curated list above belong here rather than being turned away.*

*Nothing listed yet.*


## Cross-references

- The architectures themselves are under [Generative models](../methods/generative.md).
- Parton distributions, global fits and recasting are under [Phenomenology](phenomenology.md).
- Gradients through the simulation chain are under [Differentiable programming](../methods/differentiable.md).
- Sampling for lattice gauge theory is under [Lattice field theory](lattice.md).
