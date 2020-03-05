---
layout: page
title: Publication
permalink: /publication/
---

### Journals

Yang, Y., & Mémin, E. (2019). Estimation of physical parameters under location uncertainty using an ensemble2–expectation–maximization algorithm. Quarterly Journal of the Royal Meteorological Society, 145(719), 418-433. [file](https://github.com/eatgreen/eatgreen.github.io/raw/master/data/Yang_Memin_2019_QJRMS.pdf)

Yang, Y., & Mémin, E. (2017). High-resolution data assimilation through stochastic subgrid tensor and parameter estimation from 4DEnVar. Tellus A: Dynamic Meteorology and Oceanography, 69(1), 1308772. [file](https://github.com/eatgreen/eatgreen.github.io/raw/master/data/Yang_Memin_2017_TellusA.pdf)

Yang, Y., Robinson, C., Heitz, D., & Mémin, E. (2015). Enhanced ensemble-based 4DVar scheme for data assimilation. Computers & Fluids, 115, 201-210. [file](https://github.com/eatgreen/eatgreen.github.io/raw/master/data/Yang_et_al_2015_C%26F.pdf)

### Conferences

Yang, Y., Heitz, D., & Mémin, E. (2019). Lagrangian particle image velocimetry. In 13th International
Symposium on Particle Image Velocimetry, ISPIV 2019. [file](https://github.com/eatgreen/eatgreen.github.io/raw/master/data/Yang_el_al_2019_ISPIV.pdf)

Yang, Y., Heitz, D., & Mémin, E. (2018, September). An ensemble filter estimation scheme for Lagrangian trajectory reconstruction. In Congrès Francophone de Techniques Laser, CFTL 2018. [file](https://hal.archives-ouvertes.fr/hal-02097724/file/CFTL_article_Yang_etal.pdf)

Cai, S., Mémin, E., Yang, Y., & Xu, C. (2018, June). Sea Surface Flow estimation via Ensemble-based variational data assimilation. In 2018 Annual American Control Conference (ACC) (pp. 3496-3501). IEEE. [file](https://hal.inria.fr/hal-01589637/document)

Yang, Y., & Mémin, E. (2018, September). Estimating physical parameter of stochastic dynamical system using an ensemble2-expectation-maximization algorithm. CNA 2018 - Colloque National d'Assimilation de Données, Rennes, FR [file](https://www.lebesgue.fr/sites/default/files/webform/Estimating_physical_parameter_Yang_etal.pdf)

Yang, Y., Cai, S., Mémin, E. & Heitz, D. (2017). Ensemble-Variational methods in data assimilation. in 2nd 'CFD for PIV' Workshop, Delft, NL [file](https://hal.archives-ouvertes.fr/hal-01671751/document)

### Working papers and technique reports

Yang, Y. (2020). Ensemble Data Assimilation and Function Approximation: A kernel view. Technique report. [file](https://hal.archives-ouvertes.fr/hal-02496158)

Weaver, A. T., Chrust, M., Ménétrier, B., Yang, Y., Piacentini, A., Tshimanga, J., ... & Zuo, H. (2018). Using Ensemble-estimated Background Error Variances and Correlation Scales in the NEMOVAR System. In Report TR/PA/18/15 (p. 39). CERFACS, Toulouse, France. [file](https://pdfs.semanticscholar.org/0b50/85ec89555f56b3420098c6d466c998d36773.pdf)

### Other international publications (posters)

Yang, Y., Heitz, D., & Mémin, E. (2018, September). Lagrangian trajectory reconstruction using ensemble-based data assimilation technique: a first approach. CNA 2018 - Colloque National d'Assimilation de Données, Rennes, FR 

Yang, Y., & Weaver A. (2016). Development of D-EVIL strategy in ensemble generation in NEMOVAR. CNA 2016 - Colloque National d'Assimilation de Données, Grenoble, FR 

Yang, Y., Robinson, C., Heitz, D., & Mémin, E. (2014). A variational ensemble scheme for noisy image data assimilation. EGU 2014 - European Geophysics Union. Vienne. AT. [file](https://meetingorganizer.copernicus.org/EGU2014/EGU2014-13434-2.pdf)

### Software

#### Ensemble Variational Data Assimilation System

- website: [http://bitbucket.org/eatgreen/envar](http://bitbucket.org/eatgreen/envar)
- Objective of the software: This software implements the EnVar method in [Yang et al.,2015, Yang & Mémin, 2017], used for data assimilation in geophysics and fluid dynamics applications. This software is a library that can be readily integrated with any fluid dynamical models.
- Users community: Fluid dynamics research and industrial.
- Size: 5000 lines written in C++, parallel computing enabled by OpenMPI.

#### En2EM, Ensemble$^2$-EM lib for physical parameter estimation

- Website: [http://bitbucket.org/eatgreen/en2em](http://bitbucket.org/eatgreen/en2em)
- Objective of the software: This software implements the En2EM method proposed in paper [Yang & Mémin, 2019], used for dynamical model learning and state estimation in geophysics and fluid dynamics applications. This software is a library that can be readily integrated with any fluid dynamical models. Besides, the expectation step of this software can be replaced by other existing data assimilation approach. 
- Users community: Geophysical community and fluid dynamics community.
- 10000 lines written in Matlab. 

#### KLPT/LAPIV, Kernelized Lagrangian Particle Tracking/Lagrangian PIV

- website: [http://bitbucket.org/eatgreen/klpt-lapiv](http://bitbucket.org/eatgreen/klpt-lapiv)
- Objective of the software: This software implements the kernalized LPT method \cite{Yang18} and the Lagrangian PIV method \cite{Yang19c}. The objective is to reconstruct Eulerian velocity or Lagrangian particle positions from stereographic images. This software is a standalone application but can be also integrated into other projects as a library.
- Users community: Experiment fluid dynamics and signal processing community.
- Size: 15000 lines written in C++. Extensive use of OpenCV library. Parallel computing enable by TBB and CUDA. This software also supports PyTorch C++ API. A small portion of code is written in Python for post-processing, visualization and project building.


<!-- This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)

You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll) -->


<!-- [jekyll-organization]: https://github.com/jekyll -->
