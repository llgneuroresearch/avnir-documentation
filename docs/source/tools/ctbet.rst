CTbet
=====

CTbet is a tool for extracting brain regions from CT images using a Docker container.

Installation
------------

To use CTbet, you need to have Docker installed on your system. See :ref:`docker`.

Usage
-----

1. Pull the CTbet Docker image:

.. code-block:: bash

    docker pull llgneuroresearch/ctbet

2. Run the CTbet Docker container:

.. code-block:: bash

    docker run -ti -v /path/to/your/data:/input -v /path/to/your/output:/output -u 0:$(id -g) --gpus all --rm --shm-size 2g avnirlab/ctbet:latest -device cuda

Replace `/path/to/your/data` with the path to your data directory, and `/path/to/your/output` with the desired path to your output directory.
The `--device cuda` flag permits to run the inference on GPU. If you want to run the inference on CPU, you can replace `cuda` by `cpu`.

Example
-------

Here is an example command to run CTbet:

.. code-block:: bash

    # Create input and output directories
    mkdir output_directory
    ls input_data/
        image1.nii.gz  image2.nii.gz
    
    # Run CTbet
    docker run -ti -v $(pwd)/input_data:/input -v $(pwd)/output_directory:/output \
    -u 0:$(id -g) --gpus all --rm --shm-size 2g avnirlab/ctbet:latest -device cuda
    
    # Check the output
    ls output_directory/results
        image1.nii.gz  image2.nii.gz  dataset.json
        plans.json  predict_from_raw_data_args.json


