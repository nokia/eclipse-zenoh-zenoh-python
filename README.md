![zenoh banner](./zenoh-dragon.png)

![Build](https://github.com/eclipse-zenoh/zenoh-python/workflows/Python%20package/badge.svg)
[![Documentation Status](https://readthedocs.org/projects/zenoh-python/badge/?version=latest)](https://zenoh-python.readthedocs.io/en/latest/?badge=latest)
[![Gitter](https://badges.gitter.im/atolab/zenoh.svg)](https://gitter.im/atolab/zenoh?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![License](https://img.shields.io/badge/License-EPL%202.0-blue)](https://choosealicense.com/licenses/epl-2.0/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# Eclipse zenoh Python API

[Eclipse zenoh](http://zenoh.io) is an extremely efficient and fault-tolerant [Named Data Networking](http://named-data.net) (NDN) protocol 
that is able to scale down to extremely constrainded devices and networks. 

The Python API is for pure clients, in other terms does not support peer-to-peer communication, can be easily tested against a zenoh router running in a Docker container (see https://github.com/eclipse-zenoh/zenoh#how-to-test-it). 

-------------------------------
## How to install it

The version 0.5.0 of this zenoh-python API is under development.  
Currently, the only way to install it is to [build it](#how-to-build-it) from sources.
 based on the new zenoh Rust code ([zenoh rust-master branch](https://github.com/eclipse-zenoh/zenoh/tree/rust-master))

### Supported Python versions and platforms

zenoh-python has been tested with Python 3.5, 3.6, 3.7 and 3.8.

It relies on the [zenoh](https://github.com/eclipse-zenoh/zenoh/tree/rust-master/zenoh) Rust API which require the full `std` library. See the list Rust supported platforms here: https://doc.rust-lang.org/nightly/rustc/platform-support.html .

Currently only the following platforms have been tested:
 * Linux
 * MacOS X


-------------------------------
## How to build it

Requirements:
 * Python >= 3.5
 * A virtual environement such as [venv](https://docs.python.org/3/library/venv.html), [miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Conda](https://docs.conda.io/projects/conda/en/latest/)
 * [Rust and Cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html).
   Then install the __*nighlty*__ toolchain running:
   ```bash
   rustup toolchain install nightly
   ```
 * [maturin](https://github.com/PyO3/maturin). Install it with:
    ```bash
   pip install maturin
   ```

Steps:
 * Make sure your shell is running in a Python virtual environment.
 * Clone the branch **rust-master** of the [zenoh](https://github.com/eclipse-zenoh/zenoh) repository:
   ```bash
   git clone https://github.com/eclipse-zenoh/zenoh.git -b rust-master
   ```
 * In the same directory, clone the **branch_0.5.0_dev** of this repository:
   ```bash
   git clone https://github.com/eclipse-zenoh/zenoh-python.git -b branch_0.5.0_dev
   ```
 * Build zenoh-python using **maturin**
    ```bash
   cd zenoh-python
   maturin develop
   ```

Maturin will automatically build the zenoh Rust API, as well as the zenoh-python API and install it in your Python virtual environement.

-------------------------------
## Running the Examples

_TODO_