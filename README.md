# crosskit-x86_64-darwin-libpython

This repository contains the `libpython` libraries and headers for the x86-64
macOS, in order to facilitate non-x86-64 to x86-64 macOS cross compilation of
the programs that depend on the `libpython` library (e.g. GDB).

__SUPERHACK WARNING!__ This repository also contains a special shell script
(`${LIBPYTHON_KIT_ROOT}/bin/python`) to allow the GDB build system to resolve
the `include` and `lib` paths for the host Python.

## Build GDB

```
/usr/local/src/gdb-9.1/configure \
    --build=aarch64-apple-darwin \
    --host=x86_64-apple-darwin \
    --target=arm-none-eabi \
    --prefix=<OUTDIR> \
    --with-python=${LIBPYTHON_KIT_ROOT}/bin/python
```
