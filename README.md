# Singularity R

[![Continuous Integration Status](https://github.com/nickjer/singularity-r/workflows/Continuous%20Integration/badge.svg)](https://github.com/nickjer/singularity-r/actions)
[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

Singularity image for [R].

This is still a work in progress.

## Build

You can build a local Singularity image named `singularity-r.sif` with:

```sh
sudo singularity build singularity-r.sif singularity-r.def
```

## Deploy

Instead of building it yourself you can download the pre-built image from the
[Cloud Library](https://cloud.sylabs.io/library) with:

```sh
singularity pull singularity-r.sif library://nickjer/default/singularity-r:4.2.0
```

> **WARNING:** This pre-built image comes with OpenBLAS installed using the
> Debian binary packages. Be sure to run any tests with libraries that leverage
> OpenBLAS in your enviroment. If you notice any odd results it may be best to
> build this image from scratch on the machine you intend to run it on. See
> instructions under the Build section above.
>
> Or alternatively you can mount the locally installed OpenBLAS library into
> the container using...
>
> ```sh
> singularity run \
>   --bind "/path/on/host/to/libopenblas.so:/usr/lib/R/lib/libblas.so.3" \
>   singularity-r.sif
> ```

## Run

### R

The `R` command is launched using the default run command:

```sh
singularity run singularity-r.sif
```

or as an explicit app:

```sh
singularity run --app R singularity-r.sif
```

Example:

```console
$ singularity run --app R singularity-r.sif --version
R version 4.2.0 (2022-04-22) -- "Vigorous Calisthenics"
Copyright (C) 2022 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
https://www.gnu.org/licenses/.
```

### Rscript

The `Rscript` command is launched as an explicit app:

```sh
singularity run --app Rscript singularity-r.sif
```

Example:

```console
$ singularity run --app Rscript singularity-r.sif --version
Rscript (R) version 4.2.0 (2022-04-22)
```

## Contributing

Bug reports and pull requests are welcome on GitHub at
https://github.com/nickjer/singularity-r.

## License

The code is available as open source under the terms of the [MIT License].

[R]: https://www.r-project.org/
[MIT License]: http://opensource.org/licenses/MIT
