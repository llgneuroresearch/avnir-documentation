.. _nextflow:

Nextflow
========

Nextflow is a powerful and flexible workflow management system. Follow these steps to install Nextflow on your system.

Prerequisites
-------------

Before installing Nextflow, ensure you have the following prerequisites:

- Java 17 or later installed on your system. You can check your Java version by running:

    .. code-block:: bash

         java -version

- If Java is not installed, you can install it using the following commands:

    .. code-block:: bash

         sudo apt update
         sudo apt install openjdk-17-jdk

Installation
------------

1. Download the Nextflow installation script using `curl`:

     .. code-block:: bash

            curl -s https://get.nextflow.io | bash

2. Make the script executable:

     .. code-block:: bash

            chmod +x nextflow

3. Move the `nextflow` executable to a directory in your PATH, for example:

     .. code-block:: bash

            mv nextflow /usr/local/bin/

4. Verify the installation by running:

     .. code-block:: bash

            nextflow -v

     This should display the installed version of Nextflow.

Congratulations! You have successfully installed Nextflow on your system. You can now start creating and running workflows.