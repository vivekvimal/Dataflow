# Dataflow

Instrauction to Set up your environment

To Check your Python version
The Beam SDK requires Python 2 users to use Python 2.7 and 
Python 3 users to use Python 3.5 or higher. Check your version by running:

python --version
Install pip
pip --version

If you do not have pip version 7.0.0 or newer, run the following command to install it. This command might require administrative privileges.

pip install --upgrade pip
Install Python virtual environment

It is recommended that you install a Python virtual environment for initial experiments. 
If you do not have virtualenv version 13.1.0 or newer, run the following command to install it. This command might require administrative privileges.

pip install --upgrade virtualenv

pip install --upgrade setuptools

Get Apache Beam

Create and activate a virtual environment
A virtual environment is a directory tree containing its own Python distribution. To create a virtual environment, create a directory and run:

virtualenv /path/to/directory

A virtual environment needs to be activated for each shell that is to use it. Activating it sets some environment variables that point to the virtual environment’s directories.

To activate a virtual environment in Bash, run:

. /path/to/directory/bin/activate
That is, execute the activate script under the virtual environment directory you created.

Install the latest Python SDK from PyPI:
pip install apache-beam

Extra requirements
The above installation will not install all the extra dependencies for using features like the Google Cloud Dataflow runner. 
Information on what extra packages are required for different features are highlighted below. 

Google Cloud Platform
Installation Command: pip install apache-beam[gcp]

# As part of the initial setup, install Google Cloud Platform specific extra components. Make sure you
# complete the setup steps at /documentation/runners/dataflow/#setup
pip install apache-beam[gcp]
python3 -m apache_beam.examples.wordcount --input gs://dataflow-samples/shakespeare/kinglear.txt \
                                         --output gs://<your-gcs-bucket>/counts \
                                         --runner DataflowRunner \
                                         --project your-gcp-project \
                                         --region your-gcp-region \
                                         --temp_location gs://<your-gcs-bucket>/tmp/
