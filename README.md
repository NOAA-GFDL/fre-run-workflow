# fre-run-workflow
The `fre-run-workflow` repository holds GFDL's next-generation FRE (FMS Runtime Environment) workflow configuration template for the running a model. This workflow will be able to support production and regression cycles that will utilize fre-cli subtools to stage input files (to set up a working directory), run the model executable or container, configure restart files, stage output files, transfer model output to PP/AN (if wanted), and run FRE Canopy post-processing (using the fre-postprocess-workflow) (if wanted).

This workflow template utilizes Cylc, a general purpose workflow engine that is very efficient for cyclic systems.For more information, see [cylc's user guide here](https://cylc.github.io/cylc-doc/stable/html/user-guide/index.html).

## Model Running Instructions (to be updated/developed)

### Setup
### Guide/more info

## Quickstart (to be updated/developed)

If on Gaea, follow the instructions below: 

```
# Load FRE
module load fre/<version>

# NOT YET DEVELOPED - will replace commands below
# fre workflow all -y [model yaml file] -e [experiment name] -p [platform] -t [target]

git clone https://github.com/NOAA-GFDL/fre-run-workflow.git ~/cylc-src/run-wf-test
cylc install run-wf-test
cylc validate run-wf-test
#cylc play run-wf-test
```

## Developer Overview and Instructions (to be updated)

### `Cylc` Configuration
For an overview on cylc configurations, see [here](https://github.com/NOAA-GFDL/fre-postprocess-workflow/blob/main/for-developers.md#cylc-configuration-)

### Cylc Platforms
### Cylc Workflows

## Contributing Guidelines (to be added)
