
Demonstration of pip bug report https://github.com/pypa/pip/issues/7817

```
python -m venv venv
source venv/bin/activate
pip install -U pip setuptools

pip install git+https://github.com/TD22057/ipybug
```

Look at `venv/bin/ipy_script.py`, the shebank line will be:

```
#!/path/to/venv/bin/python

print("Testing 1 2 3")
```

but the original script in the repository is this:

```
#!/bin/env ipython

print("Testing 1 2 3")
```

