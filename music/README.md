# music - An executable

The `music` executable is a <SUMMARY-OF-FUNCTIONALITY>.

Note that the `music` executable in this package provides `build2` metadata.


## Usage

To start using `music` in your project, add the following build-time
`depends` value to your `manifest`, adjusting the version constraint as
appropriate:

```
depends: * music ^<VERSION>
```

Then import the executable in your `buildfile`:

```
import! [metadata] <TARGET> = music%exe{<TARGET>}
```


## Importable targets

This package provides the following importable targets:

```
exe{<TARGET>}
```

<DESCRIPTION-OF-IMPORTABLE-TARGETS>


## Configuration variables

This package provides the following configuration variables:

```
[bool] config.music.<VARIABLE> ?= false
```

<DESCRIPTION-OF-CONFIG-VARIABLES>