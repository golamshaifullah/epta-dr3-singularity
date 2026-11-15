# Third-party software

This repository provides Apptainer containers for scientific research.

The container images install publicly available scientific software from their respective upstream sources. Each component retains its original copyright and licensing terms, which are not modified or superseded by this repository.

The original Apptainer recipes, GitHub Actions workflows, and supporting scripts are separately licensed under BSD-3-Clause (see [LICENSE](LICENSE)).

## Software inventory

| Software | Version / revision | Upstream |
|---|---|---|
| Tempo2 | `b6cd5b164f6bc519a40e76744fd5bf0543c88815` | [ipta/tempo2](https://github.com/ipta/tempo2) |
| CALCEPH | 5.0.1 | [IMCCE](https://calceph.imcce.fr/) |
| PGPLOT | 5.2.2 | [Ubuntu](https://packages.ubuntu.com/noble/pgplot5) |
| GCC / gfortran | 16.2 | [GNU](https://gcc.gnu.org/) |
| OpenBLAS | 0.3.34 | [OpenMathLib](https://github.com/OpenMathLib/OpenBLAS) |
| FFTW | 3.3.11 | [FFTW](https://fftw.org/) |
| Boost | 1.92.0 | [Boost](https://www.boost.org/) |
| LAPACK | 3.12.1 | [Reference-LAPACK](https://github.com/Reference-LAPACK/lapack) |
| enterprise | 3.5.0 (`c55d2dd`) | [nanograv/enterprise](https://github.com/nanograv/enterprise) |
| PINT | 1.1.7 | [nanograv/PINT](https://github.com/nanograv/PINT) |
| corner | 2.3.0 | [dfm/corner.py](https://github.com/dfm/corner.py) |
| ArviZ | 1.3.0 | [arviz-devs/arviz](https://github.com/arviz-devs/arviz) |
| NumPyro | 0.22.0 | [pyro-ppl/numpyro](https://github.com/pyro-ppl/numpyro) |
| discovery | 0.5.1 | [nanograv/discovery](https://github.com/nanograv/discovery) |
| jexplore | 0.0.2 (`d062f6a`) | [lisa-apc/jexplore](https://gitlab.in2p3.fr/lisa-apc/jexplore) |
| JAX / jaxlib | 0.8.3 | [jax-ml/jax](https://github.com/jax-ml/jax) |

The container images are built from the upstream software distributions under the terms of their licenses. 
