Pipelines
=========

VoluLabel-Flow
--------------

This pipeline is used to compute volumetric analysis on labels. Here is a brief overview of the pipeline:

| 1) Perfom quality controls on labels and volumes.
| 2) (Optional) Compute the brain mask using the CTBET model.
| 3) Compute the volume on every label for each subject.
| 4) Merge the results in a single CSV file.


Requirements
++++++++++++

To run the pipeline, you need to have the following software installed:
:ref:`docker` or Singularity, :ref:`nextflow`.


Installation
++++++++++++

To run the pipeline, use the following example:

.. code-block:: bash

    nextflow pull llgneuroresearch/Volulabel-flow -r main
    nextflow run llgneuroresearch/Volulabel-flow -r main --input input -with-profile docker

To get the help message, run:

.. code-block:: bash

    nextflow run llgneuroresearch/Volulabel-flow -r main --help

Description
+++++++++++

``--input``: Path to the input folder containing the data. The input folder should have the following structure:

.. code-block::

    [root]
    ├── S1
    │   ├── *labels.nrrd
    │   ├── *volume.nrrd
    │   └── *brain_mask.nii.gz (optional)
    └── S2
        ├── *labels.nrrd
        ├── *volume.nrrd
        └── *brain_mask.nii.gz (optional)

The results will be written in the ``results`` folder or in the folder given with ``--output_dir`` option.

Optional Arguments
++++++++++++++++++

| ``--run_volumetry_labels``: Run volumetry on labels. By default, true
| ``--run_ct_bet``: Run CT BET. By default, true. If true, the pipeline will run CT-BET on the volumes except if a brain_mask.nii.gz image is available in the subject input foler.
| ``--custom_qc_config``: YAML config file to perform quality controls on labels. By default, use the yaml in the container.
| ``--output_dir``: Directory where to write the final results. By default, will be in "./results".

Available Profiles
++++++++++++++++++

To use the pipeline with different profiles, use the ``-with-profile`` option. The available profiles are:

| ``docker``: Use Docker containers.
| ``apptainer``: Use Apptainer containers.
| ``singularity``: Use Singularity containers.
| ``slurm``: Use Slurm executor.

When running on a local compute, we recommend using the ``docker`` profile. If running on a SLURM cluster, use the ``slurm,apptainer`` or ``slurm,singularity`` profiles. 
