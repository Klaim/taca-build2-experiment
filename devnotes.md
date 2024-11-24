
- build2 seems to work well with WASI SDK's clang, except for these points:
  - when building libraries, `-rpath` is passed to `wasm-ld` which doesnt know that flag apparently;
  - `-s` in `config.cxx.coptions` will make `bdep init` fail with a weird error because of a conflict between c and cxx modules, not sure what's going on there - compare the flags I ended up removing and the original commands (in [taca/examples/cpp/music/build.sh](https://github.com/contextfreeinfo/taca/blob/main/examples/cpp/music/build.sh))

- using iostream will result in runtime errors (taca-specific?)
- using `#include <print>` will result in link-time errors (wasi-specific?)
- need to find an easier way to generate the `taca` file than relying on environment providing `lz4`
- build2 doesnt use `.wasm` automatically for the build outputs
- find a way to generalize glsl file -> spirv -> C
- build2 fails to install the library because it tries to generate shared/static versions of it (it's binless):
    $ b install
    pc builds\wasi\libtaca-cpp\taca\liba{taca} -> builds\wasi\libtaca-cpp\taca\pca{taca}
    pc builds\wasi\libtaca-cpp\taca\libs{taca} -> builds\wasi\libtaca-cpp\taca\pcs{taca}
    pc builds\wasi\libtaca-cpp\taca\lib{taca} -> builds\wasi\libtaca-cpp\taca\pc{taca}
    error: incompatible builds\wasi\libtaca-cpp\taca\libs{taca} build
      info: library is built for install
      info: while updating (for install) builds\wasi\music\music\exe{music}
      info: while updating (for install) builds\wasi\music\music\file{music.taca}
      info: while updating (for install) builds\wasi\music\music\file{music.taca}
      info: while updating (for install) builds\wasi\music\dir{music\}
      info: while updating (for install) builds\wasi\dir{music\}
      info: while updating (for install) dir{.\}
    info: failed to update (for install) dir{.\}

