# Pegasus WMS

## Overview

Pegasus WMS is an Open OnDemand Batch Connect app that launches a JupyterLab instance with HTCondor and PegasusWMS as an interactive web server session on HPC clusters. It is designed for users who wants to execute scientific workflows.

- Upstream project: [software homepage](https://pegasus.isi.edu/)

## Features

- Launches JupyterLab+HTCondor+Pegasus via web server on compute nodes
- Supports submitting Pegasus jobs to Slurm

## Requirements

### Compute Node Software

- Conda installed environment (described below)

### Open OnDemand

- Scheduler: Slurm

## App Installation

```bash
cd /var/www/ood/apps/sys

git clone https://github.com/pegasus-isi/bc_pegasus_wms.git

```

### Software install

Create a Conda install with the required software. Note that this should not be containerized - running natively allows closer integration with Slurm.


    $ mkdir -p /some-shared-fs/pegasus
    $ wget -O miniforge.sh https://github.com/conda-forge/miniforge/releases/download/26.7.2-0/Miniforge3-26.7.2-0-Linux-x86_64.sh
    $ bash miniforge.sh -b -p $(pwd)/6.0
    $ source $(pwd)/6.0/etc/profile.d/conda.sh
    $ conda activate
    $ conda install jupyterlab htcondor click
    $ conda install https://download.pegasus.isi.edu/pegasus/6.0.0.dev0/pegasus_wms-6.0.0.dev0-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl

## Contributing

Contributions are welcome. To contribute:

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/my-improvement`)
3. Submit a pull request with a description of your changes

For bugs or feature requests, [open an issue](https://github.com/pegasus-isi/bc_pegasus_wms/issues).

This app is part of the [OOD Appverse](https://ondemand.connectci.org/affinity-groups/ood-appverse). Join the [Appverse Affinity Group](https://ondemand.connectci.org/affinity-groups/ood-appverse) to connect with other contributors.

## References

<!-- Credit upstream projects and any code you borrowed. -->

- [Pegasus WMS](https://pegasus.isi.edu/) — the application launched by this OOD app
- [Open OnDemand](https://openondemand.org/) — the HPC portal framework

## License

[MIT License](LICENSE)

## Acknowledgments

This work is supported by the National Science Foundation award number 2138286.

