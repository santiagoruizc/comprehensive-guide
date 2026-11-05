## Section 3: Environment management & Jupyter kernel registration

### 3.1 Create and activate virtual environment
Isolate dependencies per project to avoid version conflicts.

```bash
# Create environment with specified Python version
conda create -n bio_env python=3.11 -y

# Activate the environment
conda activate bio_env

# Deactivate when work is complete
conda deactivate
```

### 3.2 Register environment to Jupyter / VS Code
Enable the isolated Conda environment to run inside Jupyter Notebooks (.ipynb) and Visual Studio Code:

```bash
# Install ipykernel inside the active environment
conda install ipykernel -y

# Register environment as a Jupyter Kernel
python -m ipykernel install --user --name=bio_env --display-name "Python (bio_env)"

# List all registered kernels
jupyter kernelspec list
```