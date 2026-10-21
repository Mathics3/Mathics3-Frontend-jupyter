# Mathics3 Jupyter Kernel

This provides a Jupyter Kernel for running Mathics3. In contrast to code in [Mathics3-Frontend-notebooks](https://github.com/Mathics3/Mathics3-Frontend-notebooks), this is a full Kernel rather than an extension to be loaded on top of Python 3 `ipykernel`.

## Using

After the Mathics3 Jupyter kernel is loaded, you can enter Mathics3 commands, and you will get the results evaluated and displayed.

There are two "magic" commands available, `%pip` and `%python`.

### `%pip`

The `%pip` command allows you to run Python "pip" commands or to see information on installed Python packages.


### `%python` or `%py`

The `%python` command allows you to run Python statements or evaluate Python expressions, rather than Mathics3 expressions or statements.

A special variable `session` is defined so that you have access to the underlying Python session.

## Building

Install all of the prerequisites:

```console
$ pip install -e .
```

Register the Mathics3 kernel for Jupyter via the JSON file `mathics3-jupyter/kernel.json`.

```console
$ python3 -m mathics3_jupyter_kernel.install_kernel
```

This needs to be done only once.

To see that this has been installed, run:

```console
$ jupyter kernelspec list

Available kernels:
  ...
  mathics3-kernel                 /home/rocky/.local/share/jupyter/kernels/mathics3-kernel
  ...
```

Run a Jupyter notebook:

```
$ jupyter notebook # --notebook-dir=...
...
    To access the server, open this file in a browser:
        file:/home/rocky/.local/share/jupyter/runtime/jpserver-XXXXX-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/tree?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
        http://127.0.0.1:8888/tree?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

```

Or inside Jupyter, you can als

```
%load_ext mathics3_kernel.frontend.jupyter
```

Here is a [sample notebook](examples/jupyter-notebook.ipynb)
that can be used with a local Jupyter installation.

## Running

```console
$ jupyter lab  # or:  make lab
```

## Debugging

Install `jupyter-console` and run `jupyter console` via `make`:

```console
$ make console
jupyter console --kernel=mathics3-jupyter
Jupyter console 6.6.3

Mathics3 10.0.2dev0 Kernel (1.0)- A Mathematica-compatible engine
...
```
