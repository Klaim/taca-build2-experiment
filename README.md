# taca-build2-experiments - <SUMMARY>

This is an attempt to
- build a C++ taca example from https://github.com/contextfreeinfo/taca/ using `build2`
- then convert the C++ code to use C++ modules

**THIS IS AN EXPERIMENT, IN NO WAY IT IS DESIGNED FOR ANY KIND OF OTHER USAGE**

The C++ source code is from `679dbc7` in https://github.com/contextfreeinfo/taca/

Requirements:
 - `taca`: the executable must be available for use, see  https://github.com/contextfreeinfo/taca/
   - The simplest way is to build it using `cargo` (Rust), see the instructions in the Readme
   - The name `taca` will be used by test runners, so it needs to be available at test time
 - WASI SDK (provides the toolchain, including clang, and will build for WASM32)
 - `lz4` (to create `.taca` files)
 - `naga` must be available: `cargo install naga-cli`
 - You need to use the flags from the config in `build2-configs/wasi.config` (see below for the `bdep init` command)

For example:

```
git clone .../taca-build2-experiments.git
cd taca-build2-experiments

PATH="$PATH/<path to taca build dir>"
bdep init -C builds/wasi @wasi cc "config.cxx='<path to WASI SDK>/bin/clang++'" config.config.load=./build2-configs/wasi.config
bdep update # or `b` or `b update: music/`
bdep test # or `b test` or `b test: music/`
```

