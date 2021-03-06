## Development Guide
This document is intended to be the canonical source of truth for things like supported toolchain versions for building Kloader.
If you find a requirement that this doc does not capture, please submit an issue on github.

This document is intended to be relative to the branch in which it is found. It is guaranteed that requirements will change over time
for the development branch, but release branches of Kloader should not change.

### Build Kloader
Some of the Kloader development helper scripts rely on a fairly up-to-date GNU tools environment, so most recent Linux distros should
work just fine out-of-the-box.

#### Setup GO
Kloader is written in Google's GO programming language. Currently, Kloader is developed and tested on **go 1.8.3**. If you haven't set up a GO
development environment, please follow [these instructions](https://golang.org/doc/code.html) to install GO.

#### Download Source

```console
$ go get github.com/appscode/kloader
$ cd $(go env GOPATH)/src/github.com/appscode/kloader
```

#### Install Dev tools
To install various dev tools for Kloader, run the following command:
```console
$ ./hack/builddeps.sh
```

#### Build Binary
```
$ ./hack/make.py
$ kloader version
```

#### Dependency management
Kloader uses [Glide](https://github.com/Masterminds/glide) to manage dependencies. Dependencies are already checked in the `vendor` folder.
If you want to update/add dependencies, run:
```console
$ glide slow
```

#### Generate CLI Reference Docs
```console
$ ./hack/gendocs/make.sh
```
