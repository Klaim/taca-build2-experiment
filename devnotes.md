
- build2 seems to work well with WASI SDK's clang, except for these points:
  - when building libraries, `-rpath` is passed to `wasm-ld` which doesnt know that flag apparently;
  - `-s` in `config.cxx.coptions` will make `bdep init` fail with a weird error because of a conflict between c and cxx modules, not sure what's going on there - compare the flags I ended up removing and the original commands (in [taca/examples/cpp/music/build.sh](https://github.com/contextfreeinfo/taca/blob/main/examples/cpp/music/build.sh))

- using iostream will result in runtime errors
- using `#include <print>` will result in link-time errors
