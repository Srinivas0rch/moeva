# MoEvA2 Replication

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
# [![arXiv](https://img.shields.io/badge/arXiv-2112.01156-b31b1b.svg)](https://arxiv.org/abs/2112.01156)

This study aims to reprodue the experiments in the paper [A Unified Framework for Adversarial Attack and Defense in Constrained Feature Space](https://arxiv.org/abs/2112.01156). 

## Introduction

## Create the environment

From WSL2 and the in the repo directory,

execute "docker build -t moeva-rep ." to build the docker using Dockerfile.

Then start the docker interactively with "docker run -it -v $(pwd):/app moeva-rep"

This will also mount the project directory you are in, inside the docker. 

Then from this interactive docker, you can activate the environment (conda activate moeva2) and run the experiments (./run_all.sh)

<!-- Additional data has been downloaded from https://figshare.com/s/84ae808ce6999fafd192 for reproduction of the experiment and has been placed at moeva2/data/attack_name for respective folders. -->

## Note: Due to large size, limitation of github repository all files of the data are not available in the mentioned folder above. The additional data can be downloaded from https://figshare.com/s/84ae808ce6999fafd192

## Note 1: miniconda & python3.8.8 is recommended.

## File structure
- Dockerfile: Downloads docker container (miniconda 3) and installs the required dependencies from requirements.txt & scipy==1.4.0 thereby setting up the environment required to run the experiments.
- config: configurations files for preparing and running the experiments.
- data: has all the data for the attacks.
- models: models which are pre-trained.
- out: contains the experimental results.
- src: modules and scripts to run the experiment(s).
  - attacks: has the implementation of the attack modules.
  - examples: usecase based scripts.
  - botnet and lcld: contains the scripts of LCLD & CTU-13 data and models respectively.
  - united: has single script to run combined attack(s).

The results are found in ./out/attacks/[project]/rq[X]/metrics_[attack_name]_[hash].json
## PS: project is lcld or botnet and X = 1/2/3/4

## The experiments were run with 400 generations(budget) where there was 4000 (for LCLD) and 100 in the case of botnet (CTU-13) where there was 1000. Also, the cores were reduced from 10 to 1 at ./config/rq1.botnet.static.yaml due to system limitation(s) in the case of botnet experiment(s).
