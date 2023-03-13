TODO: notebooks are not necessary for streamlit, so remove ipykernel, by updating the script with an argument
## Setup
To run the code on a local or remote machine, you can follow the recommendation below.
We use `pip` and `venv`, which are the default Python environment management system and are effective for that purpose.
### Prerequisite
* The code was tested using `Python` 3.10.10, and the environment was set up using `pip` and `venv` (rather than `conda`). The instructors use `vscode` as the IDE.
* Make sure you have a compatible version of Python (3.7.x-3.10.x) and the necessary tools `pip` and `git` installed. You can check if they are installed and see their versions by running `python --version`, `pip --version` (or `pip3 --version`), and `git --version` in the command line. If any of these are missing, please install them according to the official guides: [python](https://www.python.org/downloads/), [pip](https://pip.pypa.io/en/stable/installation/) and [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
### Setup Steps
1. To get a local copy of this repository, run `git clone GITHUB_URL` in the command line, where `GITHUB_URL` is the url of the repository. This will create a new sub-folder with a local copy of the repository. Note that if you encounter any issues during the setup process below, you can delete this folder and start fresh by cloning again. The changes made during the setup should only affect files within this folder, so deleting it will give you a clean slate to work from. If there are any issues with the set up, make sure to have a look at the notes below.
2. The goal of the setup process is to create a virtual environment. The required packages as defined in the `requirements.txt` files will be installed in the environment. Next, `ipykernel` will be installed. There are two ways to accomplish this, so you can choose the method that works best for you:
    1. **Semi-automatically using the `setup.py` script**: From the repository root folder, run `python ./setup/setup.py`. This should complete all required steps for you. If you get no error, the setup should be completed, and you could verify it by testing it as described below. This script was tested on Windows 11. If it does not work and you are unable to quickly debug the issue, simply delete the folder, go back to step 1, and try the manual version instead. Deleting the folder will revert any changes made. It may also be helpful to spend a few minutes reviewing `setup.py` to see how it implements the manual steps below.
    2. **Manually** - following the steps below in the command line:
        1. Create a subfolder named `venv` within the local repository folder, i.e. by `mkdir venv`
        2. `cd` into `venv` and initialize two environments by running:
            * `python -m venv streamlit_simple`
        3. `cd` out back to the repository root folder, and activate the `streamlit_simple` virtual environment by running:
            * Linux or Mac: `source ./venv/streamlit_simple/bin/activate` 
            * Windows CMD: `.\venv\streamlit_simple\Scripts\activate.bat`
            * Windows Powershell: `.\venv\streamlit_simple\Scripts\Activate.ps1`
         4. Install the packages: `pip install -r requirements_streamlit_simple.txt`
         5. Install `ipykernel`: `python -m ipykernel install --user --name=treamlit_simple --display-name=treamlit_simple`
         6. Deactivate the environment by: `deactivate`

### Setting Up `vscode` to work with Notebooks and Virtual Environments
* `vscode` needs to be restarted after setting up the virtual environments for the first time. Otherwise, the environments will not be visible in `vscode`.
* To run Python notebooks in `vscode`, you first need to install the `Python` extension by Microsoft (done via the Extensions menu on the left sidebar).
* Then, open a notebook and set the right kernel (either `treamlit_simple`). Setting the kernel is done on the top right side in `vscode`. 
* Note that if you see wiggly orange lines below the package names in the import statement, change the interpreter to that of the virtual environment by typing in the command-palette `Python: Select Interpreter` ([stackoverflow](https://stackoverflow.com/a/72721797/10006823)).

### Testing the Setup
TODO: add a testing file and doc

### Notes
* For a good context about Python's `venv` module, see its (well-written) [official doc](https://docs.python.org/3/tutorial/venv.html))
* Your Python executable might be `python3` rather than `python` (e.g. as in Ubuntu 22.04 due to a [historical root-casue](https://itsfoss.com/python-not-found-ubuntu/#:~:text=It's%20because%20the%20Python%20language,available%20as%20python%20package%2Fexecutable.)). In that case simply replace `python` with `python3` above, and in the manual method below, if you decide to run it.
* In case you want to have multiple Python versions on the same machine (e.g. because you have Python 3.11 installed and the setup below fails for that reason), then you can do so by installing each version to a different folder. Python installation are completely independent of each other. Then, in the steps described below, call the Python version based on its path. `which python` (Linux&Mac) and `where python` (windows) commands tells you which python path is being called by `python`. See [stackoverflow](https://stackoverflow.com/questions/2547554/multiple-python-versions-on-the-same-machine) for more. Importantly, once you install the virtual environments as described above, and using the right python version, a copy of that version is created in the virtual environment. So that when you activate the environment as usual, the right python version will be used. A second option is to use `pyenv`. `pyenv` is a good way to manage several python versions running on the same machine, and allows you to pick a global version or set it locally for one project ([realpython](https://realpython.com/intro-to-pyenv/)).