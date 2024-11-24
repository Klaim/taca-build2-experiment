# taca-build2-experiments - <SUMMARY>

`taca-build2-experiments` is a <SUMMARY-OF-FUNCTIONALITY>.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`taca-build2-experiments` in your `build2`-based project, then instead see the accompanying
package [`README.md`](<PACKAGE>/README.md) file.

The development setup for `taca-build2-experiments` uses the standard `bdep`-based workflow.
For example:

```
git clone .../taca-build2-experiments.git
cd taca-build2-experiments

bdep init -C builds/wasi @wasi cc "config.cxx='<path to WASI SDK>\bin\clang++'"
bdep update
bdep test
```
