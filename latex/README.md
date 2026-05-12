### 1. Install MacTeX

```url
https://www.tug.org/mactex/mactex-download.html
```

### 2. Go to VSCode, and check if:

```bash
which latexmk
```
returns something.

### 3. Install `LaTeX workshop` extension

### 4. cmd + shift + P > Preferences: Open User Settings (JSON)

### 5. It should look like this:

```json
{
    "window.commandCenter": true,
    "remote.SSH.remotePlatform": {
        "vastai": "linux",
        "ysdc": "linux",
        "mcml": "linux"
    },
    "isort.interpreter": [
        "/nas/home/juyeop/miniconda3/envs/pi/bin/python3"
    ],
    "remote.autoForwardPortsSource": "hybrid",
	
    //add this here
    "latex-workshop.latex.tools": [
    {
        "name": "latexmk",
        "command": "/Library/TeX/texbin/latexmk",
        "env": {
        "PATH": "/Library/TeX/texbin:/usr/bin:${env:PATH}"
        },
        "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOC%"
        ]
    }
    ]
}
```

### 6. Free to use!