Avnirpy
=======

Avnirpy is a library developed by Avnir Lab under the direction of Dr. Letourneau Guillon. It includes a range of tools primarily designed for CT scans segmentation and analysis.

Prerequisites
-------------

Before installing Avnirpy, ensure you have the following prerequisites:

- Python >= 3.9 and < 3.12 installed on your system. You can check your Python version by running:

    .. code-block:: bash

         python3 --version

- Git installed on your system. If not installed, you can install Git using the following commands:

    .. code-block:: bash

         sudo apt update
         sudo apt install git

We highly recommend using a virtual environment to manage your Python dependencies. You can create a virtual environment by following the :ref:`python` documentation. 

Installation
------------

You can install Avnirpy by cloning the repository and using `pip`. Run the following command to install Avnirpy:

.. code-block:: bash

    git clone git@github.com:llgneuroresearch/avnirpy.git
    cd avnirpy
    pip install -e .

To test your installation, you can run the following command:

.. code-block:: bash

    avnir_print_header.py -h

Example
-------

Here is an example command to run Avnirpy script:

.. code-block:: bash

    # Create input and output directories
    ls input_data/
        image1.nii.gz
    
    # Run Avnirpy
    python avnir_print_header.py input_data/image1.nii.gz

    # Command line output
    <class 'nibabel.nifti1.Nifti1Header'> object, endian='<'
    sizeof_hdr      : 348
    data_type       : b''
    db_name         : b''
    extents         : 0
    session_error   : 0
    regular         : b''
    dim_info        : 0
    dim             : [  3 512 512  34   1   1   1   1]
    intent_p1       : 0.0
    intent_p2       : 0.0
    intent_p3       : 0.0
    intent_code     : none
    datatype        : float32
    bitpix          : 32
    slice_start     : 0
    pixdim          : [1.       0.488281 0.488281 5.373771 1.       1.       1.       1.      ]
    vox_offset      : 0.0
    scl_slope       : nan
    scl_inter       : nan
    slice_end       : 0
    slice_code      : unknown
    xyzt_units      : 2
    cal_max         : 0.0
    cal_min         : 0.0
    slice_duration  : 0.0
    toffset         : 0.0
    glmax           : 0
    glmin           : 0
    descrip         : b''
    aux_file        : b''
    qform_code      : unknown
    sform_code      : aligned
    quatern_b       : 0.0
    quatern_c       : -0.18652385
    quatern_d       : 0.9824504
    qoffset_x       : 125.0
    qoffset_y       : 139.38208
    qoffset_z       : -7.3461156
    srow_x          : [ -0.488281   0.         0.       125.      ]
    srow_y          : [  0.         -0.4543053  -1.969492  139.38208  ]
    srow_z          : [ 0.         -0.17895542  4.999852   -7.3461156 ]
    intent_name     : b''
    magic           : b'n+1'

Every scripts available are in the `avnirpy/scripts` directory. They all begin with `avnir_`. If you want 
to know more about the scripts, you can run the script with the `-h` option.
