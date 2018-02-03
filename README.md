# Singularity R

[![Singularity Hub](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/462)
[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

Singularity image for [R].

This is still a work in progress.

## Build

You can build a local Singularity image named `singularity-r.simg` with:

```sh
sudo singularity build singularity-r.simg Singularity
```

## Deploy

Instead of building it yourself you can download the pre-built image from
[Singularity Hub](https://www.singularity-hub.org) with:

```sh
singularity pull --name singularity-r.simg shub://nickjer/singularity-r
```

## Run

### R

The `R` command is launched using the default run command:

```sh
singularity run singularity-r.simg
```

or as an explicit app:

```sh
singularity run --app R singularity-r.simg
```

Example:

```console
$ singularity run --app R singularity-r.simg --version
R version 3.4.3 (2017-11-30) -- "Kite-Eating Tree"
Copyright (C) 2017 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
http://www.gnu.org/licenses/.
```

### Rscript

The `Rscript` command is launched as an explicit app:

```sh
singularity run --app Rscript singularity-r.simg
```

Example:

```console
$ singularity run --app Rscript singularity-r.simg --version
R scripting front-end version 3.4.3 (2017-11-30)
```

## Contributing

Bug reports and pull requests are welcome on GitHub at
https://github.com/nickjer/singularity-r.

## License

The code is available as open source under the terms of the [MIT License].

[R]: https://www.r-project.org/
[MIT License]: http://opensource.org/licenses/MIT
