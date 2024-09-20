---
title: 'HDMod: A Fortran program for exact derivative calculations in scientific programs'
tags:
  - Fortran
  - derivative calculation
  - sensitivity calculation
  - chemical tranpsort models
authors:
  - name: Jiachen Liu
    orcid: 0009-0004-9331-3168
    equal-contrib: true
    affiliation: 1
  - name: Shannon L. Capps
    orcid: 0000-0002-6872-6604
    equal-contrib: true
    affiliation: 1
affiliations:
 - name: Department of Civil, Architectural, & Environmental Engineering, Drexel University, USA
   index: 1
   ror: 04bdffz58
date: 20 September 2024
bibliography: paper.bib

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/xxxxx <- update this with the DOI from AAS once you know it.
aas-journal: Astrophysical Journal <- The name of the AAS journal.
---

# Summary

The calculation of derivatives in scientific programs is essential to a number of
applications. Derivatives inform scientists about how particular output variables 
will respond to changes in particular input variables. The calculation of exact 
derivatives in complex models remain a challenge because of the difficulty to 
write out exact equations. Linear approximation of derivatives is prone to truncation 
and cancellation errors. We developed a program which applies a numerical technique
that can compute the exact first- and second-order derivative of a model output
variable with respect to one or two input variable. This program is invaluable to
fields including simulation of weather and air pollutants in the atmosphere, and 
can be applied to other fields including finance and engineering, where derivatives
are of interest to the users of the program. 

# Statement of need

`HDMod` is a module which defines the operation principles of hyperdual numbers. Fike and Alonso
proposed the calculation of derivatives using hyperdual numbers in 2011 [@Fike:2011]. 
Because of the delicate definition of hyperdual numbers, the first- and second-order 
derivatives calculated by the method is free from traditionally existing truncation 
and cancellation errors. 

`HDMod` was originally developed for application in the Community Multiscale Air 
Quality model (CMAQ) [@Liu:2024]. First- and second-order derivatives of pollutant
concentrations with respect to emissions were presented in the Liu, 2024 paper. 
In theory, `HDMod` can be applied to other field where derivatives are of interest
to researchers, and traditional method doesn't yield a good result due to subtractive 
cancellation and truncation errors. 

# Mathematics

Single dollars ($) are required for inline mathematics e.g. $f(x) = e^{\pi/x}$

Double dollars make self-standing equations:

$$\Theta(x) = \left\{\begin{array}{l}
0\textrm{ if } x < 0\cr
1\textrm{ else}
\end{array}\right.$$

You can also use plain \LaTeX for equations
\begin{equation}\label{eq:fourier}
\hat f(\omega) = \int_{-\infty}^{\infty} f(x) e^{i\omega x} dx
\end{equation}
and refer to \autoref{eq:fourier} from text.

# Citations

Citations to entries in paper.bib should be in
[rMarkdown](http://rmarkdown.rstudio.com/authoring_bibliographies_and_citations.html)
format.

If you want to cite a software repository URL (e.g. something on GitHub without a preferred
citation) then you can do it with the example BibTeX entry below for @fidgit.

For a quick reference, the following citation commands can be used:
- `@author:2001`  ->  "Author et al. (2001)"
- `[@author:2001]` -> "(Author et al., 2001)"
- `[@author1:2001; @author2:2001]` -> "(Author1 et al., 2001; Author2 et al., 2002)"

# Figures

Figures can be included like this:
![Caption for example figure.\label{fig:example}](figure.png)
and referenced from text using \autoref{fig:example}.

Figure sizes can be customized by adding an optional second parameter:
![Caption for example figure.](figure.png){ width=20% }

# Acknowledgements

This work is supported by National Science Foundation CAREER Award grant no. 1944669 to Shannon L. Capps. We also want to acknowledge the contribution from Ryan P. Russell for providing a testing framework of the multicomplex numbers, which inspired the development of a testing framework for the hyperdual numbers. 

# References
