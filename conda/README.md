### Stop Conda from activating `base` by default

Run:
```bash
conda config --set auto_activate_base false
```
Then restart terminal.

To re-enable it:
```bash
conda config --set auto_activate_base true
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