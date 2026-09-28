About aresys-io-feedstock
=========================

Feedstock license: [BSD-3-Clause](https://github.com/conda-forge/aresys-io-feedstock/blob/main/LICENSE.txt)

Home: https://github.com/aresys-srl/aresys_io

Package license: MIT

Summary: Python library for reading and writing Aresys EO/SAR product formats.

Documentation: https://opensource.aresys.it/aresys_io

# Aresys Formats Input/Output (aresys_io)

**Aresys I/O (`aresys_io`)** is the official Aresys Python library for reading, writing, and manipulating Aresys Earth Observation (EO) and Synthetic Aperture Radar (SAR) product formats.

Designed to be modular, independent, and extensible, `aresys_io` provides unified data access and metadata management across the entire SAR processing and simulation pipeline. It is built to integrate with [**PERSEO**](https://github.com/aresys-srl/perseo) ([docs](https://opensource.aresys.it/perseo)), the Aresys modular framework for Earth Observation and SAR data handling.

## Supported Formats & Core Features

`aresys_io` provides complete support for the core internal Aresys formats:

- **Product Folder (PF)**: The official Aresys SAR product format for organizing and storing data and auxiliary information. Supports **Level 0 (RAW)**, **Level 1 (SLC / GRD)**, and **Interferometric** products across multi-swath and multi-polarization channels with dedicated XML annotations, binary/TIFF raster data, manifests, and preview overlays.
- **Point Target Binary**: Dedicated format for discrete radar reflectors (such as corner reflectors, active radar calibrators, or synthetic point scatterers) used in SAR simulation, calibration, and IRF analysis. Stores 3D Cartesian coordinates ($X, Y, Z$) and full polarimetric radar cross sections ($HH, HV, VH, VV$) with support for memory-mapped zero-copy access and high-level `NominalPointTarget` representations.
- **SAR System**: Serialization and handling of SAR system and simulation parameters, including trajectory state vectors, timeline tables, swath parameter tables, and satellite definitions.
- **Metadata & Raster Engine**: Robust XML serialization/deserialization for Aresys metadata schemas, orbit and attitude modeling, polynomial conversions, and flexible 2D raster I/O.

Current build status
====================


<table><tr>
    <td>All platforms:</td>
    <td>
      <a href="https://github.com/conda-forge/aresys-io-feedstock/actions/workflows/conda-build.yml">
        <img src="https://github.com/conda-forge/aresys-io-feedstock/actions/workflows/conda-build.yml/badge.svg?event=push&branch=main">
      </a>
    </td>
  </tr>
</table>

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-aresys--io-green.svg)](https://anaconda.org/conda-forge/aresys-io) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/aresys-io.svg)](https://anaconda.org/conda-forge/aresys-io) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/aresys-io.svg)](https://anaconda.org/conda-forge/aresys-io) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/aresys-io.svg)](https://anaconda.org/conda-forge/aresys-io) |

Installing aresys-io
====================

Installing `aresys-io` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

How to use
----------

<details>
<summary>With conda</summary>

```
conda install aresys-io
```

</details>

<details>
<summary>With mamba</summary>

```
mamba install aresys-io
```

</details>

<details>
<summary>With pixi</summary>

```
# for adding to your local project
pixi add aresys-io
# for installing globally
pixi global install aresys-io
```

</details>

Search package versions
-----------------------

It is possible to list all of the versions of `aresys-io` available on your platform:

<details>
<summary>With conda</summary>

```
conda search aresys-io --channel conda-forge
```

</details>

<details>
<summary>With mamba</summary>

```
mamba search aresys-io --channel conda-forge
```

</details>

<details>
<summary>With pixi</summary>

```
pixi search aresys-io --channel conda-forge
```

</details>

<details>
<summary>With mamba repoquery, which may provide more information</summary>

```
# Search all versions available on your platform:
mamba repoquery search aresys-io --channel conda-forge

# List packages depending on `aresys-io`:
mamba repoquery whoneeds aresys-io --channel conda-forge

# List dependencies of `aresys-io`:
mamba repoquery depends aresys-io --channel conda-forge
```

</details>


About conda-forge
=================

[![Powered by
NumFOCUS](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A)](https://numfocus.org)

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[Azure](https://azure.microsoft.com/en-us/services/devops/), [GitHub](https://github.com/),
[CircleCI](https://circleci.com/), [AppVeyor](https://www.appveyor.com/),
[Drone](https://cloud.drone.io/welcome), and [TravisCI](https://travis-ci.com/)
it is possible to build and upload installable packages to the
[conda-forge](https://anaconda.org/conda-forge) [anaconda.org](https://anaconda.org/)
channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance,
[conda-smithy](https://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information, please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating aresys-io-feedstock
============================

If you would like to improve the aresys-io recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/aresys-io-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks, and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string)
   back to 0.

Feedstock Maintainers
=====================

* [@matteoaletti](https://github.com/matteoaletti/)

