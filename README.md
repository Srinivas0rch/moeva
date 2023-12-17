# MoEvA2 Replication

<!-- [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
# [![arXiv](https://img.shields.io/badge/arXiv-2112.01156-b31b1b.svg)](https://arxiv.org/abs/2112.01156) -->

**Important notice**: 
This aims to reprodue the paper [A Unified Framework for Adversarial Attack and Defense in Constrained Feature Space](https://arxiv.org/abs/2112.01156). 

## Introduction

The package has the code and data for reproducing the research "A Unified Framework for Adversarial Attack and Defense in Constrained Feature Space".

## Create the environment

From WSL2 and the in the repo directory,

execute "docker build -t moeva-rep ." to build the docker.

Then  start the docker interactively with "docker run -it -v $(pwd):/app moeva-rep"

This will also mount the project directory you are in, inside the docker. 

Then from this interactive docker, you can activate the environment (conda activate moeva2) and run the experiments (./run_all.sh)

Additional data has been downloaded from https://figshare.com/s/84ae808ce6999fafd192 and placed in the data folder of the original data (folder) in the package.

## File structure

- config: configurations files used to prepare and run the experiments
- data: the source data used to craft the attacks
- models: pre-trained models
- out: results of the experiments
- src: scripts and modules to run the attacks
  - attacks: module containing the implementations of the attacks
  - examples: usecase-specific scripts
  - botnet and lcld: scripts to prepare data and models for the experiments for CTU-13 and LCLD respectively
  - united: scripts to run a single attack

The results are found in ./out/attacks/[project]/rq[X]/metrics_[attack_name]_[hash].json

## The experiments were run with 400 generations wherever there was 4000 and the cores were reduced from 10 to 2/1 at ./config/rq1.botnet.static.yaml due to system limitation(s).
