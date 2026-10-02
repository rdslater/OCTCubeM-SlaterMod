# Slater Mod
This is my personal fork of the OCT-Cube repository.  I am not adding much technical value, but what I am trying to do is improve the model card, setup and documentation.  I often complain about how broken OSS is, so this is my attempt to contribute and FIX the problem.  This README supports my work. The orignal (this code is forked) is at README_ORIGINAL.MD

For now my first goals are
1. Improve the install documentation (I opened an issue in the original repo, but it looks rather unattended)
2. Document the features better.  My particular interest was in the OCTCube and there are multiple models here.
3. Publish our results.  This is a personal project but I AM using this for work where we are working on OCT classification (thus my interest)
   - This allows me to document MY work and contributions to this project

## Things that do work:
- [docker](https://hub.docker.com/repositories/zucksliu)
- The Model checkpoints are on [here](https://huggingface.co/zucksliu/OCTCubeM)

## Things that may cause you grief
- Installation Instructions.  Will install and overwrite multiple versions of torch causing the flash attention to fail.  I plan to attack this first and get a stable install procedure
- Documentation--a lot of details are in the paper and not in the repository. Not everyone wants to go through a long paper to figure out model details. 


The original README.md from the authors is at README_ORIGINAL.md

## Important Items I have found so far
- Input size and orientation
Orientation is Slice x Width x Height (aka Z, X, Y). 
Ophthamology looks at B-Scans (slices with the X dimension being the "width" and the Y dimension being the "height").  Each Scan (B-Scan or "Slice" is along the Z direction) So i like to think of this (personal model) as 60 images of 256x256.  The fun part is native OCT comes in a TON of resolutions--the most common I have encountered is 97x512x496

Training size was 60x256x256 on using a VIT 3D Autoencoder with 90% masking

## TODO
- Add a diagram of an OCT

Last Updated 10-01-26
