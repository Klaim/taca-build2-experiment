# taca-build2-experiments - <SUMMARY>

`taca-build2-experiments` is a <SUMMARY-OF-FUNCTIONALITY>.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`taca-build2-experiments` in your `build2`-based project, then instead see the accompanying
package [`README.md`](<PACKAGE>/README.md) file.

The C++ source code is from `679dbc7` in https://github.com/contextfreeinfo/taca/

Requirements:
 - TACA: the executable must be available for use, see  https://github.com/contextfreeinfo/taca/
   - The simplest way is to build it using `cargo` (Rust)
 - WASI SDK (provides the toolchain)
 - `lz4` (to create `.taca` files)
 - `naga` must be available: `cargo install naga-cli`
 -

For example:

```
git clone .../taca-build2-experiments.git
cd taca-build2-experiments

PATH="$PATH/<path to taca build dir>"
bdep init -C builds/wasi @wasi cc "config.cxx='<path to WASI SDK>/bin/clang++'" config. config.config.options=./build2-configs/wasi.config
bdep update
bdep test
```
