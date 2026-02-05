---
lang: fr
title: Boolean Satisfiability and the DPLL Algorithm
author: Léo \textsc{Leesco}
date: Jeudi 5 février 2026
---

Pour des raisons purement pratiques, je préfère utiliser les idées du sujet sans utiliser directement les implémentations proposées. Ce faisant, je "généralise" un peu les notations, en espérant qu'elles me permettent de prouver les résultats attendus :

- ne plus faire de modification en place sur l'`assignment` permet d'adopter une solution purement fonctionnelle, que j'espère plus simple à prouver
- on ne restreint plus explicitement les clauses à exactement 3 littéraux :
    * ceci permet de terminer immédiatement l'algorithme lorsqu'on a une clause vide ; on doit satisfaire une union vide de litéraux, et étant donné que l'élément neutre pour l'union est $\bot$
    * lorsqu'on n'a plus de clauses à traiter, de même que dans le cas de l'union, on se trouve dans une intersection vide, qui est donc vraie.

# SAT Solver

