# fre-run-workflow
The `fre-run-workflow` repository holds GFDL's next-generation FRE (FMS Runtime Environment) workflow configuration template for running a model. This workflow will be able to support production and regression cycles that will utilize fre-cli subtools to stage input files (to set up a working directory), run the model executable or container, configure restart files, stage output files, transfer model output to PP/AN (if wanted), and run FRE Canopy post-processing (using the fre-postprocess-workflow) (if wanted).

This workflow template utilizes Cylc, a general purpose workflow engine that is very efficient for cyclic systems. For more information, see [cylc's user guide here](https://cylc.github.io/cylc-doc/stable/html/user-guide/index.html).

## Model Run Workflow (to be updated)

The `flow.cylc` workflow definition file details how a model in run at GFDL. Breaking down it's components, the file has 4 main sections:

- `[meta]`: Defines metadata for the workflow such as "title", "description, and "url"
- `[scheduler]`: Defines settings for the scheduler
- `[scheduling]`: Defines the task graph that determines when each task should run and if they are dependent on another 
- `[runtime]`: Defines task scripts, environment variables, and tools to be run

This runtime workflow will follow the process of setting up a working directory, running the model executable or container, configuring restart files, and staging the output to get ready for transfers. If wanted, the workflow will also have the ability to transfer model output from Gaea to PPAN and run FRE Canopy post-processing. 

For GFDL production models, the runtime workflow will cycle over a `BATCH_CYCLE` recurrence interval. This variable will be determined by the `production wallclock` and `production segment runtime` set in the YAML configurations. 

For GFDL regression models, the workflow tasks will run once for different regression types. Examples can include, but are not limited to, `basic`, `debugrts`, and `timing`.

## Model Running Quickstart (to be updated/developed)

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
### Cylc Tips and Tricks
- `Cylc` Configuration: [overview of global.cylc](https://github.com/NOAA-GFDL/fre-postprocess-workflow/blob/main/for-developers.md#cylc-configuration-)
- `Cylc` platforms:
    - the platforms most notably include the `host` name, `job runner`, and `install` target, where cylc can install job files
    - platforms are set for any workflow to use in the global.cylc configuration file.
    - To view configured platforms available: `cylc config --platform-names`
    - To view platform configurations: `cylc config --platforms`
- `Cylc` workflow monitoring: [GUI, TUI, CLI tips](https://github.com/NOAA-GFDL/fre-postprocess-workflow/blob/main/for-developers.md#cylc-workflow-monitoring-)

### Running and testing workflows (more in depth for developer; to be added)

## Contributing Guidelines (to be added)
