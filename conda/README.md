### Stop Conda from activating `base` by default

Run:
```bash
conda config --set auto_activate false
```
Then restart terminal.

To re-enable it:
```bash
conda config --set auto_activate true
```


### Make a different environment activate automatically

To activate `myenv` whenever a terminal opens instead of `base`:

For **bash**:
```bash
echo 'conda activate myenv' >> ~/.bashrc
```

For **zsh**:
```bash
echo 'conda activate myenv' >> ~/.zshrc
```

Then restart terminal or run:
```bash
source ~/.bashrc
```


### Check available `cudatoolkit` versions for a specific Python version

Check all available `cudatoolkit` builds:
```bash
conda search -c conda-forge cudatoolkit
```

Test compatibility with a specific Python version (e.g., 3.10):
```bash
conda create -n test-cuda --dry-run python=3.10 cudatoolkit -c conda-forge
```

Check a specific CUDA version:
```bash
conda create -n test-cuda --dry-run python=3.10 cudatoolkit=11.8 -c conda-forge
```

Check PyTorch + Python 3.10 + CUDA 11.8:
```bash
conda create -n test --dry-run python=3.10 pytorch pytorch-cuda=11.8 -c pytorch -c nvidia
```


### Conda env pops up after disabling it in .bashrc

VS Code often auto-activates the selected Python environment in new terminals.

Open VS Code settings and search:
```
Python: Terminal Activate Environment
```

Disable it, or add this to `settings.json`:
```json
{
  "python.terminal.activateEnvironment": false
}
```