# Charged Black Hole Mergers: Orbit Circularisation and Chirp mass Bias
Containing code used in our article with the above title.

## OrbitEvol.ipynb
Code used in first part of the paper, plotting analytical solutions and performing numerics for evolving orbital parameters under back-reaction of the electromagnetic emission. If you want to change the initial conditions/step-size/other, be sure that the code stops evolving a parameter once it reaches zero within some tolerance for these new choices. Plots used in paper produced by the code as it is.

## MatchedFilterMockv3.ipynb
(Newer and improved code from the third version of the paper)
Code used in second part of the third version of the paper, creating mock strains and uncharged templates, matching them with each other to study bias in chirp mass induced by charged signals. Logic in code described in paper. Based on tutorial from LIGO open science center found [here](https://www.gw-openscience.org/GW150914data/LOSC_Event_tutorial_GW150914.html#Matched-filtering-to-find-the-signal). Set EVENT parameter to decide which of the source parameters listed in the table of the paper to run for. Beware of long runtimes. If you want to use this code and runtimes are an issue, we suggest following optimalisations:
* Match the initial phase analytically. This is partly described in Maggiore vol 1 page 389.
* Port functions to Fortran (or C) and include them to the notebook using f2py (or C equivalent). Be sure that your noise spectral density comes out right. You can find it by Welch decomposition. Be also sure that you are wary of Fourier conventions, especially in constructing your LIGO-noise.
* Parallelise other parts of the code than the chirp bias finder. As of now, everything beneath the chirp mass bias finder runs in serial code.

## MatchedFilterMock.ipynb and MatchedFilterMockv2.ipynb
Codes used in the second parts of the first and second versions of the paper. Kept as documentation. However, MatchedFilterMockv3 is recommended to use instead, due to various improvements (listed in the beginning of the file). TLDR: Do not use this.

-----------------

Both codes can be run by using jupyter notebook, or jupyter lab.

For any questions or comment on my code or the paper, you can reach me on mailto:oyvind.christiansen@astro.uio.no
