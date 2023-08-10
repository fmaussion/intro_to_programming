# Installing python packages

This chapter contains instructions about how to install 
additional packages useful for scientific programming

## Prerequisites

- you have a working python installation based on mambaforge ([Week 01](../week_01/01-Installation.ipynb)) 
- you have installed jupyterlab ([Week 02](../week_02/01-Install-jupyter.ipynb))
- you understood the differences between the **windows prompt**, the **miniforge prompt**, the **python 
interpreter**, the **ipython interpreter**, and **jupyterlab**. 

```{warning} 

If you still have doubts about all these terms, don't hesitate to revisit the installation instructions in 
weeks [01](../week_01/01-Installation.ipynb) and [02](../week_02/01-Install-jupyter.ipynb), as well
as the video in week [03](../week_03/01-Intro-notebooks.ipynb)
```

(install-mamba)=
## Context: conda environments

When you open the **miniforge prompt**, you are opening a windows prompt with new tools available:
for one, `python` is installed and can be run. Similarly, `conda` and `mamba` commands are only available from the miniforge 
prompt, and not from the standard prompt.
This is possible thanks to [conda](https://docs.conda.io), which is a package management system for python. 
Conda gives you access to a very large number of python packages *for free* (the only think you'll need is an 
internet connection, to connect to the package servers).

```{admonition} More details on miniforge and mamba
:class: dropdown, note

I asked you to insall miniforge instead of "plain" conda for two main reasons: 
- miniforge is giving you access to the packages available from the [conda-forge](https://conda-forge.org), which
  is a more complete and more up-to-date repository for python packages.
- miniforge has `mamba` installed per default. `mamba` is a drop-in replacement for `conda`, and is significantly faster. You don't need 
  to know why at this stage: just follow my instructions and you will be fine. 

```

You will recognize that you are using conda thanks to the following indices:
- when opening the miniforge prompt, a `(base)` text appears in front of the current path. For Jane, a 
  typical miniforge prompt looks like: `(base) C:\Users\Jane>`
- when Jane asks her computer where to find python, conda is indicating the `python.exe` that came with the conda installation.

You can ask for the location of a specific prompt command with the command `where`. 
For Jane, the miniforge prompt gives the following indications about the location of `python`:

```none
(base) C:\Users\Jane> where python 
C:\Users\Jane\mambaforge\python.exe
C:\Users\Jane\AppData\Local\Microsoft\WindowsApps\python.exe

(base) C:\Users\Jane> 
```

The first `python.exe` on the list is the one that will be used if you type `python` in the prompt.
This is precisely why conda is useful: **it clearly separates your python installation from all other contents 
on your computer**.

```{exercise}
Open a miniforge prompt and ask windows where to find your current python installation. Compare yours with Jane's.
What about the location of `ipython`? And of `jupyter-lab`? 
```

(install-env)=
## Recommended: create an environment called "inpro"

`(base)` is the name of the base (default) environment for conda. Installing further packages in `(base)` is fine,
but I recommend against it. I recommend to keep `(base)` as simple as possible, with few or no packages installed, 
and use named environments for further usages. I'll explain you why a bit later.

First, open the miniforge prompt (in `base`) and type the following command:

```none
mamba create -n inpro --clone base
```

If asked to confirm, type "yes". 

What did we just do? We created a new conda environment called "`inpro`" (this is the
purpose of the option `-n`) which clones all packages available in `base` (this last part is optional: if you omit it,
your new environment will be completely empty and you'll have to reinstall jupyter to be able to 
use it).

You can now activate your new environment with `mamba activate inpro`.

```{exercise}
Activate the new environment. What changed in comparison to `(base)`? Now ask the prompt again about where to find the commands
`ipython` and `jupyter-lab`. Can you see the difference to `base`? 
```

[Conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html) are a very simple
and elegant way to manage different installations of python packages. They allow to clearly separate different installations
and, more importantly, **conda environments allow us to make mistakes**. 

Since "environments" are nothing else than folders on your computer, they allow setups such as:
- `(base)`: python v3.9, jupyter-lab, ipython
- `(inpro)`: same as `(base)` + numpy, scipy, matplotlib
- `(test)`: python 3.10
- `(complex)`: same as `(base)` + numpy "beta version" + complicated package
- etc.

You can switch between environments with `mamba activate env_name` and leave the current environment with `mamba deactivate`.

```{important} 

When an environment is active, you can see it with the `(base)` or `(inpro)` indicator in front of the prompt. **In the 
active environment, ALL mamba commands refer to this specific environment**. 

For example, to list the packages available in `inpro`, you need to activate it first (`mamba activate inpro`) and 
*then* list the packages with `mamba list`. 

To open jupyterlab and have access the packages installed in `inpro`, activate it first and *then* start `jupyter-lab`.
```

When one of your environments becomes "broken" or obsolete, you can simply delete it with  `mamba remove -n ENVNAME --all`.
This will delete the corresponding folder and all packages in it. Creating, activating and deleting environments is super 
easy, and this is why I recommend their use.

```{admonition} Mamba/conda cheat sheet:
:class: note

- `mamba create -n inpro --clone base` : create an environment called "`inpro`" with the same packages in it as `base`
- `mamba create -n inpro` : same as above, but empty
- `mamba activate inpro` : activate the `inpro` environment
- `mamba deactivate` : leave the current environment
- `mamba info --envs` : get a list of all environments
- `mamba list` : list the currently installed packages in a specific environment
- `mamba remove -n inpro --all` : delete the inpro environment and all packages in it.
```

Visit the [conda documentation](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html#managing-environments) for more commands
(just replace all "`conda`" commands with "`mamba`").

## Required: installing additional python packages

In the course of your studies, you will be lead to install many (many) python packages, for example [xarray](https://docs.xarray.dev) for 
gridded data analysis or [MetPy](https://unidata.github.io/MetPy) for meteorology.

Almost always, the install procedure will be:
1. open the miniforge prompt
2. (optional but recommended) activate the environment where you want to install the package
3. install the package with `mamba install`

For now, I ask you to install the following python packages:
- [numpy](https://numpy.org), the fundamental package for scientific computing with Python
- [scipy](https://scipy.org), fundamental algorithms for scientific computing in Python
- [matplotlib](https://matplotlib.org), data visualization with Python

To install these, activate the `inpro` environment (recommended) or use `base`, and type:

```none
mamba install numpy scipy matplotlib
```

Answer "yes" to confirm the installation. Note that `mamba` will install several additional packages. These 
automatically installed packages are called "**dependencies**": they are required for the other packages
to function properly.

To test if the installation worked properly, open an ipython interpreter and type:

```python
In [1]: import numpy as np
In [2]: np.arange(1, 11, 2)
```

The output should be:

```python
Out[2]: array([1, 3, 5, 7, 9])
```

Congratulations! You are ready for the rest of the lecture.


## Learning checklist

<label><input type="checkbox" id="week05_01" class="box"> I understand that a **miniforge prompt** is a windows prompt with conda and python commands available</input></label>
<label><input type="checkbox" id="week05_02" class="box"> I understand that miniforge creates a folder (and sub-folders) at the location I indicated at the installation, and this is where all my python packages are installed.</input></label>   
<label><input type="checkbox" id="week05_03" class="box"> I am able to create new conda environments, activate them, and switch between them.</input></label> 
<label><input type="checkbox" id="week05_04" class="box"> I understand that packages installed with `mamba install ...` are always installed in the environment which is currently active. `(base)` is like any other environment: it is simply the default one. </input></label> 
<label><input type="checkbox" id="week05_05" class="box"> I understand that using environments is beneficial on the long term, because it allows me to experiment with 
  additional packages, without being afraid of breaking anything: **environments are just folders on my computer**!</input></label> 
<label><input type="checkbox" id="week05_06" class="box"> I am ab;e install new packages using `mamba`. I have installed numpy, scipy, and matplotlib.</input></label>    
