# Anomaly detection

## Overview

Anomaly detection asks whether collider data contains something the Standard Model
does not predict, without specifying in advance what that something is. It responds to
a structural tension in the search program: a dedicated search is far more sensitive
to the signal it was designed for, but the space of possible signals is vastly larger
than the number of searches anyone can perform.

The literature divides by how much supervision is available, and that distinction
matters more than the choice of architecture. *Unsupervised* methods flag events
improbable under a learned model of the data. *Weakly supervised* methods exploit the
expectation that a signal is localized in some variable, so a classifier separating a
signal region from sidebands approximates the optimal discriminant without ever seeing
a labeled signal. The latter has proven substantially more powerful.

A point easily missed on a first pass: the hard part is usually not the anomaly score
but the background estimate, since a selection made with a learned score distorts the
background in ways that must be controlled before any significance can be quoted.

## Recommended starting points

- **Machine Learning for Anomaly Detection in Particle Physics**, Belis et al. (2023) ([arXiv:2312.14190](https://arxiv.org/abs/2312.14190)) — *the standard review of the area; read this first*
- **Anomaly Detection for Physics Analysis and Less than Supervised Learning**, Nachman (2020) ([arXiv:2010.14554](https://arxiv.org/abs/2010.14554)) — *shorter and more conceptual, on the supervision spectrum and why weak supervision helps*
- **The LHC Olympics 2020: A Community Challenge for Anomaly Detection in High Energy Physics**, Kasieczka et al. (2021) ([arXiv:2101.08320](https://arxiv.org/abs/2101.08320)) — *the LHC Olympics summary, doubling as an empirical survey of what many methods achieve on common data*

## Curated paper list

!!! note "This list is a seed, not a curated selection"
    A few landmark papers are listed to give the section a starting shape.
    A proper curated list — thematically grouped, with an annotation on every
    entry — is what this section still needs. See [Contribute](../contribute.md).

- **Anomaly Detection for Resonant New Physics with Machine Learning**, Collins et al. (2018) ([arXiv:1805.02664](https://arxiv.org/abs/1805.02664)) — *CWoLa hunting: introduced the weakly supervised, sideband-based framing most later work builds on*
- **Searching for New Physics with Deep Autoencoders**, Farina et al. (2018) ([arXiv:1808.08992](https://arxiv.org/abs/1808.08992)) — *autoencoder reconstruction error as an anomaly score — the canonical unsupervised baseline*
- **QCD or What?**, Heimel et al. (2018) ([arXiv:1808.08979](https://arxiv.org/abs/1808.08979)) — *autoencoder jet taggers trained on QCD flag top jets well, but the reverse direction works much less well: the first sign that reconstruction error is not symmetric between signal and background*
- **Autoencoders for unsupervised anomaly detection in high energy physics**, Finke et al. (2021) ([arXiv:2104.09051](https://arxiv.org/abs/2104.09051)) — *explains that asymmetry: autoencoder scores largely track how complex an input is, so simpler signals can look more normal than the background. Worth reading before trusting any unsupervised score*
- **Anomaly Detection with Density Estimation**, Nachman et al. (2020) ([arXiv:2001.04990](https://arxiv.org/abs/2001.04990)) — *ANODE: densities estimated in signal region and sidebands separately, making the background estimate intrinsic to the method*
- **Classifying Anomalies THrough Outer Density Estimation (CATHODE)**, Hallin et al. (2021) ([arXiv:2109.00546](https://arxiv.org/abs/2109.00546)) — *CATHODE: sampling from the sideband-interpolated density to train a classifier, now a standard baseline*

## Benchmarks, datasets & software

- **The LHC Olympics 2020: A Community Challenge for Anomaly Detection in High Energy Physics**, Kasieczka et al. (2021) ([arXiv:2101.08320](https://arxiv.org/abs/2101.08320)) — *LHC Olympics 2020 R&D and black-box datasets, with a leaderboard*
- **The Dark Machines Anomaly Score Challenge: Benchmark Data and Model Independent Event Classification for the Large Hadron Collider**, Aarrestad et al. (2021) ([arXiv:2105.14027](https://arxiv.org/abs/2105.14027)) — *Dark Machines anomaly score challenge — complementary in signals and event representation*

## Open questions

*What is settled here, what is contested, and what remains unsolved? This is
the part a bibliography structurally cannot provide, and often the most
useful paragraph on the page.*

## Further reading

*Relevant work that is not an entry point — too specialized, too recent, or simply not where a newcomer should start. Suggestions that do not fit the curated list above belong here rather than being turned away.*

- **When Graph Autoencoders Look the Wrong Way: Complexity Bias and Simple Baselines in Unsupervised Anomaly Detection on the LHC Olympics 2020 Dataset**, Khan (2026) ([doi:10.5281/zenodo.23432779](https://doi.org/10.5281/zenodo.23432779)) — *a case study of the complexity bias on the LHCO R&D data: event-level graph-autoencoder scores come out inverted (AUC 0.40–0.44), while the label-free mean transverse momentum per particle reaches 0.81; argues for simple physics baselines and AUCs within multiplicity bins as standard checks*

## Cross-references

- Density estimators and flows are covered under [Generative models](../methods/generative.md).
- Real-time and trigger-level operation is under [Triggering](triggering.md).
- Significance and systematics are under [Uncertainty quantification](../methods/uncertainty.md).
