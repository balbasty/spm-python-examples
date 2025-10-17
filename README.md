# spm-python-examples

This repository contains examples that use the [Statistical Parametric Mapping](https://github.com/spm/spm) software in Python.

## Installation

### Installing the MATLAB runtime

* If you have a MATLAB license and MATLAB installed
  * Install MATLAB Compiler SDK _(Matlab > Apps > Get more apps)_

    <img width="655" height="154" alt="image" src="https://github.com/user-attachments/assets/5ef9ce89-400c-4a8b-83a7-e6b33ab2f1b0" />

* Otherwise
  * Get MATLAB Runtime [online](https://uk.mathworks.com/products/compiler/matlab-runtime.html?requestedDomain=)
  * Or follow one of the alternative steps [here[(https://github.com/spm/spm-python/tree/main?tab=readme-ov-file#installation-instructions)

### Installing Python

* You’ll need a version of Python between 3.9 and 3.12 
* On Windows, do not rely on Microsoft store’s Python
* If not sure, download Python 3.12 here: https://www.python.org/downloads/release/python-3120/

### Installing SPM-Python

* Open a terminal (in Windows, a command prompt)
* Use pip to install "spm-python" and specify your version of the MATLAB runtime:
  ```shell
  pip install spm-python[R2025b]
  ```

* Test your installation 
  * Open a Python console
    * On Windows/Linux, 	`python`
    * On Mac, 		        `mpython`

  * Start SPM:
    ```python
    from spm import spm; spm()
    ```

### Installing Jupyter

* Open a terminal (in Windows, a command prompt)
* Use pip to install "jupyter"
  ```shell
  pip install jupyter
  ```

* Make jupyter aware of your kernel
  ```shell
  python -m ipykernel install --user --name spm
  ```

* On MacOS:
  * Edit the file	`/Users/$USER/Library/Jupyter/kernels/spm/kernel.json`
  * Replace   `python`   with the output of   `which mpython`
  * Or, in one step:
    ```shell
    echo "{\"argv\": [\"$(which mpython)\", \"-m\", \"ipykernel_launcher\", \"-f\", \"{connection_file}\"], \"display_name\": \"spm\", \"language\": \"python\", \"metadata\": { \"debugger\": true}}" > "/Users/$USER/Library/Jupyter/kernels/spm/kernel.json"
    ```

## Examples

- `matlab-types`: a tutorial to the use of MATLAB data structures in Python
- `auditory_batch`: a Python reimplementation of the demo script [`auditory_spm12_batch.m`](https://www.fil.ion.ucl.ac.uk/spm/data/auditory/)
- `coreg`: a simple call to the low-level function `spm_coreg` to co-register two images
- `dcm-peb`: a Python reimplementation of Peter Zeidman's [Parametric Empirical Bayes tutorial](https://github.com/pzeidman/dcm-peb-example)
- `dcm-erp`: a DCM analysis of evoked responses

