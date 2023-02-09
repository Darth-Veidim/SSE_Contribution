---
marp: true
title: SSE Contribution
description: by Vadim Gallyamov
theme: gaia
paginate: true
_paginate: false
---

<style>
section {
  background: black;
  color: white;
  font-size: 26px;
  padding: 40px;
}

h1 {
  color: orange;
  text-align: center 
}

h2 {
  color: orange;
  text-align: left 
}

strong {
  font-weight: bold;
  color: orange;
}
  
code {
  color: orange;
  background: black;
}

</style>

# SSE Contribution to deal.II

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

:turtle: `std::pow(x,p)` <sup>1</sup> is computationally more expensive than `x * x`

In the deal.II code there exists a [function](https://www.dealii.org/current/doxygen/deal.II/namespaceUtilities.html#a834c6b595ada6f8e73c78d9bbd8ec551) `Utilities::fixed_power<p>(x)` that performs _n_ multiplications instead of _pow_ <br/> 

### Solution:

:rabbit2: Replace `std::pow(x,p)` with `Utilities::fixed_power<p>(x)` <br/><br/> 

<sup>1</sup> _with fixed integer exponent `p`_

---

## Procedure

To add the discussed changes, the following steps were taken:

:heavy_check_mark: Fork the deal.II repository, clone it locally <br/> 
:heavy_check_mark: Find all suitable files for contribution with `egrep -r 'pow.*, [2345](\.0)?\)' include/ source/` <br/> 
:heavy_check_mark: Implement changes, run `indent` check <br/> 
:heavy_check_mark: Add, commit, push, create pull request <br/> 
:x: Go through tests in `Github Actions`

---

## Problems 1

Fork was to old -> some workflows showed errors. Need to rebase:

Switch from `feature` to `master` branch <br/>
```
git checkout master
```

Add the original remote <br/>
```
git remote add upstream https://github.com/dealii/dealii
```

Update files <br/>
```
git pull upstream
git push
```

Switch back to the `feature` branch and rebase <br/>
```
git checkout darth-branch
git rebase master
git push
```
---

## Problems 2

:x: Many unnecessary commits during the work on the issue <br/>
:heavy_check_mark: Add entirely new commit that incorporates all changes

```bash
git reset --soft master
```

---




