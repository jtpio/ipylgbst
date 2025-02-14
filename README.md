
# ipylgbst

[![Github Actions Status](https://github.com/jupyterlab-contrib/ipylgbst/workflows/Build/badge.svg)](https://github.com/jupyterlab-contrib/rise/actions/workflows/build.yml) [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jupyterlab-contrib/ipylgbst/main)

A widget library for controlling LEGO® BOOST via web-bluetooth.

## Installation

You can install using `pip`:

```bash
pip install ipylgbst
```

## Development Installation

Create a dev environment:

```bash
conda create -n ipylgbst-dev -c conda-forge nodejs yarn python jupyterlab
conda activate ipylgbst-dev
```

Install the python. This will also build the TS package.
```bash
pip install -e ".[test, examples]"
```

When developing your extensions, you need to manually enable your extensions with the
notebook / lab frontend. For lab, this is done by the command:

```
jupyter labextension develop --overwrite .
yarn run build
```

Note that the `--symlink` flag doesn't work on Windows, so you will here have to run
the `install` command every time that you rebuild your extension. For certain installations
you might also need another flag instead of `--sys-prefix`, but we won't cover the meaning
of those flags here.

### How to see your changes

#### Typescript

If you use JupyterLab to develop then you can watch the source directory and run JupyterLab at the same time in different
terminals to watch for changes in the extension's source and automatically rebuild the widget.

```bash
# Watch the source directory in one terminal, automatically rebuilding when needed
yarn run watch
# Run JupyterLab in another terminal
jupyter lab
```

After a change wait for the build to finish and then refresh your browser and the changes should take effect.

#### Python

If you make a change to the python code then you will need to restart the notebook kernel to have it take effect.

## Updating the version

To update the version, install tbump and use it to bump the version.
By default it will also create a tag.

```bash
pip install tbump
tbump <new-version>
```
