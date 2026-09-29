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
For an overview on global cylc configurations and how to override them for your own testing, see [here](https://github.com/NOAA-GFDL/fre-postprocess-workflow/blob/main/for-developers.md#cylc-configuration-)

### Cylc Platforms
Cylc platforms are defined differently than GFDL/RDHPCS platforms. In `cylc`, the platforms most notably include the `host` name, `job runner`, and `install` target, where cylc can install job files. These platforms are set for any workflow to use in the global.cylc configuration file.

To view configured platforms available: `cylc config --platform-names`
To view platform configurations: `cylc config --platforms`

## Contributing Guidelines (to be added)
