# PIFFO
> Propagation d’impulsions femtosecondes dans les fibres optiques

## Objectif

L’objectif de ce projet est de développer un outil de simulation numérique permettant de modéliser la propagation d’impulsions laser ultracourtes dans les fibres optiques et d’explorer les mécanismes physiques responsables de l’élargissement spectral et de la génération de supercontinuum.
Le code de l’outil implémente la méthode Split-Step Fourier (SSFM) afin de résoudre l’équation de Schrödinger non linéaire (NLS) qui décrit la propagation d’impulsions dans les fibres optiques non linéaires et dispersives.

## Fonctionnalités

- Simuler la propagation d’impulsions dans une fibre optique
- Implémenter la méthode Split-Step Fourier
- Résoudre l’équation NLS
- Produire :
    - Evolution temporelle de l’impulsion
    - Evolution spectrale
    - Cartes 2D
- Permettre la modification des :
    - Paramètres du laser (puissance, durée de l’impulsion, longueur d’onde, forme de l’impulsion (gaussienne, gaussienne chirpée, super-gaussienne, sech2, ...))
    - Paramètres de la fibre (longueur, dispersion, coefficient nonlinéaire, ...)
- Simuler la génération de supercontinuum (l’élargissement spectral extrême, la génération de lumière blanche)

## Paramètres de simulation :

- Durée de l’impulsion $10 ps$
- Longueur de la fibre $100 km$
- Atténuation $0,2 dB/km$
- Dispersion $\beta_2 = −20 ps^2/km$
- Non-linéarité $\gamma = 10 W^{-1}/km$

## Méthode numérique

L’équation sera résolue à l’aide de la méthode Split-Step Fourier (SSFM). Cette méthode sépare la propagation en deux opérateurs :
- Opérateur linéaire (dispersion + pertes) appliqué dans le domaine fréquentiel via la transformée de Fourier.
- Opérateur non linéaire (SPM) appliqué dans le domaine temporel.

Pour un pas de propagation $\Delta z$ :
1. application de la phase non linéaire
2. transformée de Fourier
3. application de la dispersion
4. transformée de Fourier inverse

Cette méthode est très efficace pour simuler la propagation sur de longues distances.

## Références
1. G. P. Agrawal – Nonlinear Fiber Optics (2007)
2. J. M. Dudley et al. – Supercontinuum generation in photonic crystal fiber, Reviews of
Modern Physics (2006)