# This is the repo containing recipes to build contianers for epta dr3 analysis. The included software and their versions are:

## Requirements
You must have access to a linux host with appatainer or singularity. When running on HPC please ensure your HPC allows you to pull containers from the GHCR 

## Using the cntainers

To build from scratch (preferred) clone this repo on your host. Build the image using :

Build the 'base' image:
```
apptainer build --fakeroot pleb_dr3_upstream.sif 01_pleb_dr3_upstream.def
```

and then build then second layer.
```
apptainer build --fakeroot discovery_dr3_upstream.sif 02_discovery_dr3_upstream.def
```


You _must_ build the images in this order and using these image names.


## Obtaining a prebuilt image

You can pull a prebuilt image from the ghcr. 

```
apptainer pull pleb_dr3_upstream.sif oras://ghcr.io/OWNER/epta-dr3-singularity/pleb_dr3_upstream:v1.0.0
```

Verify that this image was not tampered with:
```
gh attestation verify pleb_dr3_upstream.sif \
  --repo OWNER/epta-dr3-singularity \
  --signer-workflow OWNER/epta-dr3-singularity/.github/workflows/main.yaml \
  --source-ref refs/tags/v1.0.0
```
  
Although I have made a best effort (security-wise) setup, this is not preferred for running on very critical infrastructure. If in doubt check with your HPC admin. The authors do not bear any responsibility to issues arising from the use of these prebuilt images.

## Software table

|Software	|url	|version / git-hash	|submitter	|comment|
|---------------|-------|-----------------------|---------------|-----------|
|	|	|	|	|	|
|Tempo2	|https://github.com/ipta/tempo2.git	|b6cd5b164f6bc519a40e76744fd5bf0543c88815	|golam	|safer to still use additional clockfiles from telescope owners|
|calceph	|https://calceph.imcce.fr/	|5.0.1	|golam	||
|pgplot	|https://packages.ubuntu.com/noble/pgplot5	|5.2.2	|golam	||
|gcc	|https://gcc.gnu.org/gcc-16/	|16.2	|golam	||
|gfortran	|	|16.2	|golam	||
|blas/openblas	|https://github.com/OpenMathLib/OpenBLAS/releases	|0.3.34	|golam	||
|fftw	|https://fftw.org/download.html	|3.3.11	|golam	||
|boost/libboost	|https://www.boost.org/releases/latest/	|1.92.0	|golam	||
|lapack	|https://github.com/Reference-LAPACK/lapack/releases	|3.12.1	|golam	||
|	|	|	|	||
|Enterprise	|https://github.com/nanograv/enterprise	|3.5.0 (c55d2dd)	|golam	||
|	|	|	|	||
|PINT	|https://github.com/nanograv/PINT	|1.1.7	|hippolyte	||
|corner	|https://github.com/dfm/corner.py	|2.3.0	|hippolyte	||
|arziv	|https://github.com/arviz-devs/arviz	|1.3.0	|hippolyte	||
|numpyro	|https://github.com/pyro-ppl/numpyro	|0.22.0	|hippolyte	||
|	|	|	|	||
|Discovery	|https://github.com/nanograv/discovery	|0.5.1	|golam	||
|jexplore	|https://gitlab.in2p3.fr/lisa-apc/jexplore	|0.0.2 (d062f6a)	|francesco	||
|JAX / jaxlib	|https://github.com/jax-ml/jax	|0.8.3	|francesco	||


## License

The original Apptainer definition files, GitHub Actions workflows, and associated scripts in this repository are licensed under the BSD 3-Clause License. See [LICENSE](LICENSE) for details.

The generated Apptainer/Singularity container images (`.sif`) contain third-party software distributed under its respective licenses. The BSD 3-Clause License of this repository does not supersede or replace those licenses.

Users and redistributors are responsible for complying with the applicable third-party license terms.
