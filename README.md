# fre-run-workflow
The `fre-run-workflow` repository holds GFDL's next-generation FRE (FMS Runtime Environment) workflow configuration template for the running a model. This workflow will be able to support production and regression cycles that will utilize fre-cli subtools to stage input files (to set up a working directory), run the model executable or container, configure restart files, stage output files, transfer model output to PP/AN (if wanted), and run FRE Canopy post-processing (using the fre-postprocess-workflow) (if wanted).

This workflow template utilizes Cylc, a general purpose workflow engine that is very efficient for cyclic systems.For more information, see [cylc's user guide here](https://cylc.github.io/cylc-doc/stable/html/user-guide/index.html).

# `fre-cli` Model Running Instructions

(to be added)

# Developer Instructions

(to be added)

# Contributing Guidelines

(to be added)
