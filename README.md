# jupyter_atom_virtualenv
Guide to install support for virtual environments in python inside atom, jupyter-notebook style.

I find it very useful to have jupyter notebook capabilities inside atom, trying lines of code one by one.

If you are working on several projects in parallel and have possible packets in conflict with each other, using a VENV frees from this hassle. You can activate and deactivate the VENV at choice, without impacting on the host system.


Atom support is given by [hydrogen](https://github.com/nteract/hydrogen).



A brief guide to create a VENV from scratch (instructions taken from [here](https://medium.com/@rahul3012_37725/a-very-basic-guide-to-python-virtual-environments-a53d1e191490)) and to include support for interactive kernels:
```bash
#select directory where you want venv to be stored
cd /path/to/venv/directory
#I prefer ~/.venvs, others inside project folder

#install needed packages
pip install virtualenv

#creating the environment ONLY the first time
virtualenv <my_env_name>
#it is suggested to create it inside a hidden folder in your home directory, like /home/user/.venvs

#activating the environment
source /path/to/<my_env_name>/bin/activate

#optional - install your packages
pip install <names_of_packages>
#such as
pip install -r <requirements.txt>

#to have interactive kernels (for instance for jupyter/atom)
#maybe also without '--user'
pip install --user ipykernel
python -m ipykernel install --user --name=<my_env_name>


deactivate
```

To check what kernels you have:
```bash
jupyter kernelspec list
```
To remove a kernel:
```bash
jupyter kernelspec uninstall <name_of_kernel>
```

Usual commands:
```bash
#activating the environment
source /path/to/<my_env_name>/bin/activate

#do what you have to do

#deactivate the environment
deactivate
```

The use is the same as [hydrogen](https://github.com/nteract/hydrogen). As soon as you start hydrogen, a popup comes up for you to choose the desired kernel.

Tested on MacOS Catalina 10.15.4, with Atom 1.45.0
