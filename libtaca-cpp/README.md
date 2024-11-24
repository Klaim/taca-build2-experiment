# libtaca-cpp - A C++ library

The `libtaca-cpp` C++ library provides <SUMMARY-OF-FUNCTIONALITY>.


## Usage

To start using `libtaca-cpp` in your project, add the following `depends`
value to your `manifest`, adjusting the version constraint as appropriate:

```
depends: libtaca-cpp ^<VERSION>
```

Then import the library in your `buildfile`:

```
import libs = libtaca-cpp%lib{<TARGET>}
```


## Importable targets

This package provides the following importable targets:

```
lib{<TARGET>}
```

<DESCRIPTION-OF-IMPORTABLE-TARGETS>


## Configuration variables

This package provides the following configuration variables:

```
[bool] config.libtaca_cpp.<VARIABLE> ?= false
```

<DESCRIPTION-OF-CONFIG-VARIABLES>
