# MoEvA2 Replication

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![arXiv](https://img.shields.io/badge/arXiv-2112.01156-b31b1b.svg)](https://arxiv.org/abs/2112.01156)

**Important notice**: 
The goal of this package is the replication of the experiments of the paper [A Unified Framework for Adversarial Attack and Defense in Constrained Feature Space](https://arxiv.org/abs/2112.01156). 

The latest version of our framework is available at [https://github.com/serval-uni-lu/constrained-attacks](https://github.com/serval-uni-lu/constrained-attacks).

## Introduction

This package contains all the necessary data and scripts to replicate the experiments of the research paper "A Unified Framework for Adversarial Attack and Defense in Constrained Feature Space".

## Create the environment

From WSL2 and the in the repo directory,

execute "docker build -t moeva-rep ." to build the docker.

Then  start the docker interactively with "docker run -it -v $(pwd):/app moeva-rep"

This will also mount the project directory you are in, inside the docker. 

Then from this interactive docker, you can activate the environment (conda activate moeva2) and run the experiments (./run_all.sh)

Download the additional data from https://figshare.com/s/84ae808ce6999fafd192 and place the content of the downloaded data folder in the data folder of this folder.

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

## The experiments were run with 400 dataset wherever there was 4000 and the cores were reduced from 10 to 2 at ./config/rq1.botnet.static.yaml due to system limitation(s).
