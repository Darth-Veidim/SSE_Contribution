# SSE_Contribution

by Darth-Veidim

---

## Issue Selection

Approach for a search:

- Search for issues with labels `Starter project`, `Documentation`
- Get in touch with developers

Selected issues:

1. Issue [#11529](https://github.com/dealii/dealii/issues/11529#top) - Documentation Supplementation
2. Issue [#13321](https://github.com/dealii/dealii/issues/13321) - Code Enhancement

---

## Issue 1: Documentation Supplementation

### Problem:

1. How to install documentation library (contains tutorials)?
2. How to work with tutorials?

### Solution:

1. Add the command to install `libdeal.ii-doc`
2. Add the tutorials path after installation
3. Add the command to copy and run certain tutorial

---

## Procedure

To contribute, the following steps were taken:

1. Wiki editing is restricted (forking not possible) - import wiki to local repo
2. Clone, add changes, push
3. Provide the developers with the update repository
4. Developers apply changes after review

---

## Issue 2: Code Enhancement

### Problem:

:turtle: `std::pow(x,p)` <sup>1</sup> is computationally more expensive than `p * p`

### Solution:

:rabbit2: Replace `std::pow` with multiplication


<sup>1</sup> _with fixed integer exponent `p`_
