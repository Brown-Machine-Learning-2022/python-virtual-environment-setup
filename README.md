# CS1420 Python virtual environment setup

## Python virtual env on department machines
On Brown CS department machines, the virtual environment is already built and the packages are installed. You can directly activate it and use it after sshing into the department machines

```bash
source /course/cs1420/cs142_env/bin/activate
```

The prompt will then change to `(cs142_env) $...` to show that the virtual environment is active.

deactivate the virtual environment when you're done coding with
```bash
deactivate
```

## virtual environment on personal machine 

### ensure python3.9 is installed
run the following command and make sure there's no error

On MacOS and Linux:
```bash
python3.9 -V
```

On Windows:
```
py -3.9
```

### where to put your virtual environment
We can just build one virtual environment for all CS1420 projects
```
cs1420_code/
├── env/
├── hw1/
├── hw2/
└── ...
```

### creating the virtual environment
You only need to do this once during setup. Afterwards, you can directly activate the virtual environment.

To build the virtual env, navigate the the directory that contains all your CS1420 projects, run
```bash
python3.9 -m venv env
```
to create a virtual environment contained in the folder `env`.

Or on windows, run
```
py -3.9 -m venv env
```

### activate the virtual environment
On MacOS and Linux:
```bash
source env/bin/activate
```

On Windows:
```
env\Scripts\activate
```

After activation, the prompt will change to `(env) $...` to show that the virtual environment is active.

After activation, you can call `python3.9` directly with `python`, because that is the only python version that is linked in the virtual environment.

### installing the required packages with pip
AFTER ACTIVATING THE VIRTUAL ENVIRONMENT, you can install the required packages with pip. You only need to do this once during setup.
```bash
# optional: update the essential packages
pip3 install -U pip wheel setuptools
# essential: install all CS1420 dependencies
pip3 install -r requirements.txt
```

You can find the requirements.txt in this repo (this is the same as the one on the HW1 repo).

### deactivate the virtual environment
run 
```bash
deactivate
```

After deactivation, you will notice the `(env) $...` disappearsing in the prompt. 

### installing quadprog on windows
you will need to install a C compiler on windows if you do not already have one. you can install it by doing the following

1. Download Visual Studio Build Tools (community version) https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019
2. Open the Visual Studio Installer. Download and install the Desktop Development with C++ under 'Workloads' by clicking 'Modify'.
3. Install requirements.txt as before and quadprog should work now. 
