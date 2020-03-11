# Charged Black Hole Mergers: Orbit Circularisation and Chirp mass Bias
Containing code used in our article with the above title.

## OrbitEvol.ipynb
Code used in first part of the paper, plotting analytical solutions and performing numerics for evolcing orbital parameters under back-reaction of the electromagnetic emission. If you want to change the initial conditions/step-size/other, be sure that the code stops evolving a parameter once it reaches zero within some tolerance for these new choices. Plots used in paper produced by the code as it is.

## MatchedFilterMock.ipynb
Code used in second part of the paper, creating mock strains and uncharged templates, matching them with each other to study bias in chirp mass induced by charged signals. Logic in code described in paper. Based on tutorial from LIGO open science center found [here](https://www.gw-openscience.org/GW150914data/LOSC_Event_tutorial_GW150914.html#Matched-filtering-to-find-the-signal). Plots used in paper produced by the code as it is. Beware of long runtimes. If you want to use this code and runtimes are an issue, we suggest following optimalisations:
* Match the initial phase analytically. This is partly described in Maggiore vol 1 page 389.
* Port functions to Fortran (or C) and include them to the notebook using f2py (or C equivalent). Be sure that your noise spectral density comes out right. You can find it by Wench decomposition. Be also sure that you are wary of Fourier conventions, especially in constructing your LIGO-noise.
* Parallelise other parts of the code than the chirp bias finder. As of now, everything beneath the chirp mass bias finder runs in serial code.

-----------------

Both codes can be run by using jupyter notebook, or jupyter lab.

For any questions or comment on my code or the paper, you can reach me on mailto:oyvind.christiansen@astro.uio.no
