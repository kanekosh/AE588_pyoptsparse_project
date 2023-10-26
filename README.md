# Fall 2023 AE588 pyOptSparse project

## Installation

### Docker
The easiest way to run pyOptSparse is to use [a Docker image](https://hub.docker.com/u/kanekosh/ae588public) provided by the GSI, which already installs pyOptSparse, OpenMDAO, and other dependencies.
Choose either AMD64 or ARM64 depending on the machine you have.

You can also install pyOptSparse natively on Linux or Mac (very difficult on Windows), but you're on your own if you wish to do so.
Check the [pyOptSparse documentation](https://mdolab-pyoptsparse.readthedocs-hosted.com/en/latest/install.html). You'll need to install my fork of pyOptSparse, my fork of OpenMDAO, cvxpy, and Gurobi.

### Mounting Gurobi license
Although the Docker image already installs Gurobi, you'll need a Gurobi license to solve large-scale problems.
Obviously, the Docker image does not come with the license.  
You can request a free academic license from the Gurobi's website.

Once you get the license file (`gurobi.lic` or something like that), save it on your local machine (the "host" for a Docker container), and mount the license to the Docker container.
See instructions [here](https://hub.docker.com/r/gurobi/optimizer).
(I haven't tested but it shouldn't be too complicated.)


## Examples
- `AE588_pyoptsparse_project/examples/example_openmdao.py`: OpenMDAO runscript to optimize a toy problem using IPOPT and my SQP.
- `AE588_pyoptsparse_project/examples/example_pyoptsparse.py`: pyOptSparse runscript to optimize the same toy problem using IPOPT and my SQP.

## SQP code
The SQP code is available in `/repos/pyoptsparse/pyoptsparse/pySQP/sqp.py` in the docker container.  
Feel free to modify the SQP code if needed.
Please let me know if you find a bug or any issues!
I'm pretty sure there are bugs.

The same code can be found on [GitHub](https://github.com/kanekosh/pyoptsparse/blob/sqp/pyoptsparse/pySQP/sqp.py).
See `_set_options` method for the list of options and the default values.
