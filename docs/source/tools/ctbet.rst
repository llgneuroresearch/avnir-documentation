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

    docker run -ti -v /path/to/your/data:/input -v PATH_TO_OUTPUT:/output -u 0:$(id -g) --gpus all --rm --shm-size 2g avnirlab/ctbet:latest -device cuda

Replace `/path/to/your/data` with the path to your data directory, `input_image.nii.gz` with the name of your input CT image, and `output_image.nii.gz` with the desired name for the output image.

Example
-------

Here is an example command to run CTbet:
