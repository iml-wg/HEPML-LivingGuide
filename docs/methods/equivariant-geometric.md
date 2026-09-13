# Equivariant & geometric architectures

## Overview

Physics is governed by well-known symmetries, so networks operating on physics data should have these symmetries built in rather than learning them from scratch. Equivariant networks achieve this by respecting the representation of the symmetry group under which the data transform, such that the network output transforms accordingly. Most modern deep-learning architectures are equivariant, such as CNNs for translation symmetry and transformers for permutation symmetry. For high-energy physics the explored equivariance groups are permutations of particle sets, Lorentz transformations of four-momenta, and gauge symmetry on the lattice. Equivariant networks typically outperform their non-equivariant counterparts at fixed parameter count, training data, or compute budget, although this ultimately depends on the specific equivariant architecture and the task.

## Recommended starting points

- **Symmetry Group Equivariant Architectures for Physics**, Bogatskiy et al. (2022) ([arXiv:2203.06153](https://arxiv.org/abs/2203.06153)) — *community report on benefits of equivariant architectures in high-energy physics*
- **Graph Neural Networks in Particle Physics**, Shlomi et al. (2020) ([arXiv:2007.13681](https://arxiv.org/abs/2007.13681)) — *introduction to graph networks and their application in high-energy physics*
- **Geometric Deep Learning: Grids, Groups, Graphs, Geodesics, and Gauges**, Bronstein et al. (2021) ([arXiv:2104.13478](https://arxiv.org/abs/2104.13478)) — *popular computer science review on equivariant networks, unifies CNNs, GNNs and SO(3)-equivariant networks*

## Curated paper list

*Foundational and representative work, grouped thematically. Not exhaustive by design — see [How to use this guide](../how-to-use.md).*

### Permutation-equivariant networks

- **Energy Flow Networks: Deep Sets for Particle Jets**, Komiske et al. (2018) ([arXiv:1810.05165](https://arxiv.org/abs/1810.05165)) — *Particle flow networks (PFN) achieve permutation invariance for jets using the Deep Sets approach, Energy Flow Networks (EFN) additionally add IRC safety via energy-weighted sums*
- **ParticleNet: Jet Tagging via Particle Clouds**, Qu & Gouskos (2019) ([arXiv:1902.08570](https://arxiv.org/abs/1902.08570)) — *ParticleNet: dynamic graph convolutions for jets, standard permutation-equivariant baseline architecture for jet tagging*
- **Jet tagging in the Lund plane with graph networks**, Dreyer & Qu (2020) ([arXiv:2012.08526](https://arxiv.org/abs/2012.08526)) — *LundNet: Graph network operating on the Lund tree, with nodes corresponding to declustering steps, and only three edges per node due to the tree structure*
- **Particle Transformer for Jet Tagging**, Qu et al. (2022) ([arXiv:2202.03772](https://arxiv.org/abs/2202.03772)) — *ParT: transformer with pairwise features as attention bias, the most widely used jet tagging architecture today*

### Lorentz-equivariant networks

- **An Efficient Lorentz Equivariant Graph Neural Network for Jet Tagging**, Gong et al. (2022) ([arXiv:2201.08187](https://arxiv.org/abs/2201.08187)) — *LorentzNet: message-passing graph network operating on scalar and vector representations, achieving top performance at moderate cost*
- **Explainable Equivariant Neural Networks for Particle Physics: PELICAN**, Bogatskiy et al. (2023) ([arXiv:2307.16506](https://arxiv.org/abs/2307.16506)) — *PELICAN: project four-vectors onto pairwise invariants and process them with a general set of permutation-equivariant operations on edges*
- **A Lorentz-Equivariant Transformer for All of the LHC**, Brehmer et al. (2024) ([arXiv:2411.00446](https://arxiv.org/abs/2411.00446)) — *Lorentz-equivariant Geometric Algebra Transformer (L-GATr): first Lorentz-equivariant transformer, uses geometric algebra representations (multivectors) that generalize vector representations and also include parity-odd representations*
- **Lorentz-Equivariance without Limitations**, Favaro et al. (2025) ([arXiv:2508.14898](https://arxiv.org/abs/2508.14898)) — *Lorentz Local Canonicalization (LLoCa): framework to make any network Lorentz-equivariant, enabling studies on data augmentation, symmetry breaking, and higher-order representations*

### Gauge-equivariant networks for lattice QFT

- **Equivariant flow-based sampling for lattice gauge theory**, Kanwar et al. (2020) ([arXiv:2003.06413](https://arxiv.org/abs/2003.06413)) — *gauge-equivariant normalizing flows on the lattice, based on an invariant prior distribution and gauge-equivariant coupling layers*
- **Lattice Gauge Equivariant Convolutional Neural Networks**, Favoni et al. (2020) ([arXiv:2012.12901](https://arxiv.org/abs/2012.12901)) — *L-CNN: gauge-equivariant function on the lattice, using convolutions and bilinear operations*
- **Gauge-equivariant neural networks as preconditioners in lattice QCD**, Lehner & Wettig (2023) ([arXiv:2302.05419](https://arxiv.org/abs/2302.05419)) — *gauge-equivariant function acting on fermion fields*

## Benchmarks, datasets & software

- **The Machine Learning Landscape of Top Taggers**, Kasieczka et al. (2019) ([arXiv:1902.09914](https://arxiv.org/abs/1902.09914)) — *ancient benchmark of physics-informed jet tagging architectures*
- **JetClass: A Large-Scale Dataset for Deep Learning in Jet Physics**, Qu et al. (2022) ([arXiv:2202.03772](https://arxiv.org/abs/2202.03772)) — *Modern benchmark dataset for jet taggers*

## Open questions

- Is the performance gain of equivariant networks worth their extra compute? The answer to this question likely depends on the task, the compute constraints, and the quality of the implementation.
- Can soft priors, such as data augmentation or penalty loss terms, compete with equivariant networks? This is particularly relevant for tasks with approximately realized symmetries, where equivariant networks also rely on symmetry breaking mechanisms.
- Are symmetry-informed networks useful beyond the performance increase? For instance, are they more interpretable or more robust against domain shift?
- Can networks benefit from other symmetries beyond the ones listed above? And what about more complicated representations of the established symmetry groups, such as rank-3 representations of the permutation group, rank-2 representations of the Lorentz group, or parity-odd representations?

## Further reading

*Relevant work that is not an entry point — too specialized, too recent, or simply not where a newcomer should start. Suggestions that do not fit the curated list above belong here rather than being turned away.*

- **Encoding Physics at the Precision Frontier**, Bresó-Pla et al. (2026) ([arXiv:2603.08802](https://arxiv.org/abs/2603.08802)) — *Compares Lorentz-equivariance ('explicit') with foundation models ('implicit') priors on challenging tasks in jet physics*
- **Virtues and Vices of Equivariant Transformers**, Favaro et al. (2026) ([arXiv:2608.02735](https://arxiv.org/abs/2608.02735)) — *Scaling study of Lorentz-equivariant vs. standard transformers for jet tagging under inference-cost constraints*

## Cross-references

- Equivariant generation is under [Generative models](generative.md).
- Explicit versus implicit priors is under [Foundation models](foundation-models.md).
- Cost-constrained deployment is under [Triggering](../applications/triggering.md).
- Gauge-equivariant networks for lattice QFT is under [Lattice field theory](../applications/lattice.md).
