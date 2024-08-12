# Creating Python packages with setuptools


## Building

To build the package and generate the distribution (tar.gz and whl files), use [PyPA build](https://build.pypa.io):

```bash
pip install -q build
python -m build
```

## Testing

After building your package, you can have a look if all the files are correct (nothing missing or extra), by running the following commands:

```bash
tar tf dist/*.tar.gz
unzip -l dist/*.whl
```

## References:

https://setuptools.pypa.io/en/latest/build_meta.html#building
https://setuptools.pypa.io/en/latest/userguide/package_discovery.html