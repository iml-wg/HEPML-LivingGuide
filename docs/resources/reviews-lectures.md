# Reviews & lecture notes

Reviews are the one place where this Guide does aim at completeness. A review is an
entry point by construction, and the cost of listing one more is low, so this page
carries the general reviews and lecture notes in full, together with the
topic-specific reviews that map onto a section of the Guide.

Reviews covering areas [outside our scope](../about.md) — nuclear and heavy-ion
physics, astroparticle physics, cosmology, accelerator applications — are not listed;
see [Related resources](related.md) for where those live.

## General reviews

Broad surveys of machine learning in particle physics.

- **Jet Substructure at the Large Hadron Collider: A Review of Recent Advances in Theory and Machine Learning**, Larkoski et al. ([arXiv:1709.04464](https://arxiv.org/abs/1709.04464)) — jet substructure review; the pre-ML baseline much of the tagging literature builds on.
- **Deep Learning and its Application to LHC Physics**, Guest et al. ([arXiv:1806.11484](https://arxiv.org/abs/1806.11484)) — dated in specifics, but still the clearest short account of why deep learning suited collider data.
- **Machine Learning in High Energy Physics Community White Paper**, Albertsson et al. ([arXiv:1807.02876](https://arxiv.org/abs/1807.02876)) — the community white paper that set much of the early agenda.
- **Machine learning and the physical sciences**, Carleo et al. ([arXiv:1903.10563](https://arxiv.org/abs/1903.10563)) — the wider physical-sciences context; useful for placing HEP–ML among neighboring fields.
- **Machine and Deep Learning Applications in Particle Physics**, Bourilkov ([arXiv:1912.08245](https://arxiv.org/abs/1912.08245)) — a survey of machine and deep learning applications across particle physics.
- **Modern Machine Learning and Particle Physics**, Schwartz ([arXiv:2103.12226](https://arxiv.org/abs/2103.12226)) — conceptual rather than encyclopaedic — strong on *why* physics structure belongs in the methods.
- **Machine Learning in the Search for New Fundamental Physics**, Karagiorgi et al. ([arXiv:2112.03769](https://arxiv.org/abs/2112.03769)) — oriented specifically toward searches for new physics.
- **Machine Learning**, Duarte et al. ([arXiv:2512.11133](https://arxiv.org/abs/2512.11133)) — a recent broad review of the field.
- **Building an AI-native Research Ecosystem for Experimental Particle Physics: A Community Vision**, Aarrestad et al. ([arXiv:2602.17582](https://arxiv.org/abs/2602.17582)) — a community vision for AI-native experimental particle physics; the forward-looking counterpart to the reviews above.

## Lecture notes & course material

- **Deep Learning From Four Vectors**, Baldi et al. ([arXiv:2203.03067](https://arxiv.org/abs/2203.03067)) — on learning directly from four-vectors, a good conceptual companion to the architecture literature.
- **Boosted decision trees**, Coadou ([arXiv:2206.09645](https://arxiv.org/abs/2206.09645)) — boosted decision trees — still the right tool often enough to be worth understanding properly.
- **Modern Machine Learning for LHC Physicists**, Plehn et al. ([arXiv:2211.01421](https://arxiv.org/abs/2211.01421)) — comprehensive lecture notes covering modern deep learning across LHC physics; usable as a course text.
- **QCD Masterclass Lectures on Jet Physics and Machine Learning**, Larkoski ([arXiv:2407.04897](https://arxiv.org/abs/2407.04897)) — QCD masterclass lectures on jet physics and machine learning.
- **TASI Lectures on Physics for Machine Learning**, Halverson ([arXiv:2408.00082](https://arxiv.org/abs/2408.00082)) — TASI lectures on physics *for* machine learning, including the formal-theory connections.
- **Lecture notes on Machine Learning applications for global fits**, Alda ([arXiv:2604.07520](https://arxiv.org/abs/2604.07520)) — lecture notes on ML applications for global fits.

## Community reports

- **Machine Learning and LHC Event Generation**, Badger et al. ([arXiv:2203.07460](https://arxiv.org/abs/2203.07460)) — the focused Snowmass contribution on ML for event generation.
- **Snowmass 2021 Computational Frontier CompF03 Topical Group Report: Machine Learning**, Shanahan et al. ([arXiv:2209.07559](https://arxiv.org/abs/2209.07559)) — the Snowmass computational-frontier summary of ML in HEP.
- **Snowmass Neutrino Frontier Report**, Huber et al. ([arXiv:2211.08641](https://arxiv.org/abs/2211.08641)) — the Snowmass neutrino frontier report.
- **Toward a Community Roadmap for High Energy Physics and Artificial Intelligence in China and Beyond**, Cai et al. ([arXiv:2605.03474](https://arxiv.org/abs/2605.03474)) — a recent community roadmap for HEP and artificial intelligence.

## Topic-specific reviews

Grouped by the section of the Guide they serve.

### [Anomaly detection](../applications/anomaly-detection.md)

- **Anomaly Detection for Physics Analysis and Less than Supervised Learning**, Nachman ([arXiv:2010.14554](https://arxiv.org/abs/2010.14554)) — shorter and more conceptual, on the supervision spectrum.
- **Machine Learning for Anomaly Detection in Particle Physics**, Belis et al. ([arXiv:2312.14190](https://arxiv.org/abs/2312.14190)) — the standard review of the area.
- **Unsupervised and lightly supervised learning in particle physics**, Bardhan et al. ([arXiv:2403.13676](https://arxiv.org/abs/2403.13676)) — unsupervised and lightly supervised learning more broadly.
- **Deep Learning and Model Independence**, King ([arXiv:2507.03438](https://arxiv.org/abs/2507.03438)) — on deep learning and model independence.
- **Model-Agnostic Signal Discovery with Machine Learning: Bridging the Gap Between Theory and Practice**, Amram et al. ([arXiv:2605.31103](https://arxiv.org/abs/2605.31103)) — on bridging model-agnostic methods and discovery claims.

### [Simulation & fast emulation](../applications/simulation.md)

- **Deep Generative Models for Detector Signature Simulation: An Analytical Taxonomy**, Hashemi et al. ([arXiv:2312.09597](https://arxiv.org/abs/2312.09597)) — an analytical taxonomy of generative models for detector signatures.
- **A Comprehensive Evaluation of Generative Models in Calorimeter Shower Simulation**, Ahmad et al. ([arXiv:2406.12898](https://arxiv.org/abs/2406.12898)) — a comprehensive evaluation of generative models for shower simulation.
- **CaloChallenge 2022: A Community Challenge for Fast Calorimeter Simulation**, Krause et al. ([arXiv:2410.21611](https://arxiv.org/abs/2410.21611)) — the CaloChallenge: a controlled comparison with agreed metrics.
- **A First Full Physics Benchmark for Highly Granular Calorimeter Surrogates**, Buss et al. ([arXiv:2511.17293](https://arxiv.org/abs/2511.17293)) — a full physics benchmark for highly granular calorimeter surrogates.

### [Unfolding & simulation-based inference](../applications/unfolding-inference.md)

- **The Landscape of Unfolding with Machine Learning**, Huetsch et al. ([arXiv:2404.18807](https://arxiv.org/abs/2404.18807)) — a review of ML unfolding methods with cross-method comparison.
- **A Practical Guide to Unbinned Unfolding**, Canelli et al. ([arXiv:2507.09582](https://arxiv.org/abs/2507.09582)) — a practical guide to unbinned unfolding.

### [Density estimation & likelihood ratios](../methods/density-ratio.md)

- **The frontier of simulation-based inference**, Cranmer et al. ([arXiv:1911.01429](https://arxiv.org/abs/1911.01429)) — the standard cross-disciplinary review.
- **Simulation-based inference methods for particle physics**, Brehmer et al. ([arXiv:2010.06439](https://arxiv.org/abs/2010.06439)) — the particle-physics-specific treatment.

### [Reconstruction](../applications/reconstruction.md)

- **The Machine Learning Landscape of Top Taggers**, Butter et al. ([arXiv:1902.09914](https://arxiv.org/abs/1902.09914)) — the top-tagging comparison; many architectures, one task.
- **Image-Based Jet Analysis**, Kagan ([arXiv:2012.09719](https://arxiv.org/abs/2012.09719)) — image-based jet analysis.
- **Sequence-based Machine Learning Models in Jet Physics**, de Lima ([arXiv:2102.06128](https://arxiv.org/abs/2102.06128)) — sequence-based models in jet physics.
- **High-energy physics image classification: A Survey of Jet Applications**, Kheddar et al. ([arXiv:2403.11934](https://arxiv.org/abs/2403.11934)) — a survey of jet image classification.
- **Machine Learning in High Energy Physics: A review of heavy-flavor jet tagging at the LHC**, Mondal et al. ([arXiv:2404.01071](https://arxiv.org/abs/2404.01071)) — heavy-flavour jet tagging.
- **Top-philic Machine Learning**, Barman et al. ([arXiv:2407.00183](https://arxiv.org/abs/2407.00183)) — top-philic machine learning.
- **Unveiling the Secrets of New Physics Through Top Quark Tagging**, Sahu et al. ([arXiv:2409.12085](https://arxiv.org/abs/2409.12085)) — top quark tagging.
- **Exploring jets: substructure and flavour tagging in CMS and ATLAS**, Malara ([arXiv:2410.14330](https://arxiv.org/abs/2410.14330)) — jet substructure and flavour tagging in CMS and ATLAS.
- **Run 3 performance and advances in heavy-flavor jet tagging in CMS**, CMS Collaboration ([arXiv:2412.05863](https://arxiv.org/abs/2412.05863)) — Run 3 heavy-flavour tagging performance in CMS.

### [Equivariant & geometric architectures](../methods/equivariant-geometric.md)

- **Graph Neural Networks in Particle Physics**, Shlomi et al. ([arXiv:2007.13681](https://arxiv.org/abs/2007.13681)) — an earlier and shorter GNN review.
- **Graph Neural Networks for Particle Tracking and Reconstruction**, Duarte et al. ([arXiv:2012.01249](https://arxiv.org/abs/2012.01249)) — graph networks for tracking and reconstruction.
- **Symmetry Group Equivariant Architectures for Physics**, Bogatskiy et al. ([arXiv:2203.06153](https://arxiv.org/abs/2203.06153)) — symmetry group equivariant architectures for physics.
- **Graph Neural Networks in Particle Physics: Implementations, Innovations, and Challenges**, Thais et al. ([arXiv:2203.12852](https://arxiv.org/abs/2203.12852)) — graph neural networks in particle physics.

### [Generative models](../methods/generative.md)

- **Generative Networks for LHC events**, Butter et al. ([arXiv:2008.08558](https://arxiv.org/abs/2008.08558)) — generative networks for LHC events.
- **A survey of machine learning-based physics event generation**, Alanazi et al. ([arXiv:2106.00643](https://arxiv.org/abs/2106.00643)) — a survey of ML-based physics event generation.
- **Deep Generative Models for Detector Signature Simulation: An Analytical Taxonomy**, Hashemi et al. ([arXiv:2312.09597](https://arxiv.org/abs/2312.09597)) — an analytical taxonomy of generative models for detector signatures.

### [Triggering](../applications/triggering.md)

- **Review of Machine Learning for Real-Time Analysis at the Large Hadron Collider experiments ALICE, ATLAS, CMS and LHCb**, Boggia et al. ([arXiv:2506.14578](https://arxiv.org/abs/2506.14578)) — machine learning for real-time analysis at the LHC.

### [Uncertainty quantification](../methods/uncertainty.md)

- **Dealing with Nuisance Parameters using Machine Learning in High Energy Physics: a Review**, Dorigo et al. ([arXiv:2007.09121](https://arxiv.org/abs/2007.09121)) — handling nuisance parameters with machine learning.
- **Solving Simulation Systematics in and with AI/ML**, Viren et al. ([arXiv:2203.06112](https://arxiv.org/abs/2203.06112)) — on solving simulation systematics in and with ML.
- **Uncertainty in Physics and AI: Taxonomy, Quantification, and Validation**, Haussmann et al. ([arXiv:2605.10378](https://arxiv.org/abs/2605.10378)) — on the various sources of uncertainty and their validation.

### [Lattice field theory](../applications/lattice.md)

- **Machine-learning approaches to accelerating lattice simulations**, Lawrence ([arXiv:2502.02670](https://arxiv.org/abs/2502.02670)) — ML approaches to accelerating lattice simulations.
- **Lecture Notes on Normalizing Flows for Lattice Quantum Field Theories**, Cheng et al. ([arXiv:2504.18126](https://arxiv.org/abs/2504.18126)) — lecture notes on normalizing flows for lattice QFT.

### [Phenomenology](../applications/phenomenology.md)

- **Parton distribution functions**, Forte et al. ([arXiv:2008.12305](https://arxiv.org/abs/2008.12305)) — parton distribution functions.
- **Modern Machine Learning and Particle Physics Phenomenology at the LHC**, Ubiali ([arXiv:2602.03728](https://arxiv.org/abs/2602.03728)) — modern ML and LHC phenomenology.

### [Differentiable programming](../methods/differentiable.md)

- **New directions for surrogate models and differentiable programming for High Energy Physics detector simulation**, Adelmann et al. ([arXiv:2203.08806](https://arxiv.org/abs/2203.08806)) — surrogate models and differentiable programming for HEP.
- **Toward the end-to-end optimization of particle physics instruments with differentiable programming**, Dorigo et al. ([arXiv:2203.13818](https://arxiv.org/abs/2203.13818)) — surrogate models for detector optimization white paper.

### Neutrino physics

- **A Review on Machine Learning for Neutrino Experiments**, Psihas et al. ([arXiv:2008.01242](https://arxiv.org/abs/2008.01242)) — a review of machine learning for neutrino experiments.

## Practice, reproducibility & community

- **Distributed Training and Optimization Of Neural Networks**, Vlimant et al. ([arXiv:2012.01839](https://arxiv.org/abs/2012.01839)) — distributed training and optimization of neural networks.
- **Machine Learning scientific competitions and datasets**, Rousseau et al. ([arXiv:2012.08520](https://arxiv.org/abs/2012.08520)) — on scientific competitions and datasets as a research instrument.
- **Physics Community Needs, Tools, and Resources for Machine Learning**, Harris et al. ([arXiv:2203.16255](https://arxiv.org/abs/2203.16255)) — on community needs, tools and resources for ML in physics.
- **FAIR for AI: An interdisciplinary, international, inclusive, and diverse community building perspective**, Huerta et al. ([arXiv:2210.08973](https://arxiv.org/abs/2210.08973)) — FAIR principles applied to AI in the physical sciences.
- **Les Houches guide to reusable ML models in LHC analyses**, Araz et al. ([arXiv:2312.14575](https://arxiv.org/abs/2312.14575)) — the Les Houches guide to publishing and reusing trained models — the practical prerequisite for reproducibility.
- **Novel machine learning applications at the LHC**, Duarte ([arXiv:2409.20413](https://arxiv.org/abs/2409.20413)) — novel machine learning applications at the LHC.
- **What is AI, what is it not, how we use it in physics and how it impacts... you**, David ([arXiv:2504.01827](https://arxiv.org/abs/2504.01827)) — on what AI is, what it is not, and how it is used in physics.

!!! note
    This page is curated but aims to be complete for reviews within scope. If a
    review or set of lecture notes is missing, please propose it via a
    [pull request](../contribute.md) — for this page, "is it a review, and is it in
    scope?" is the whole of the inclusion criterion.
