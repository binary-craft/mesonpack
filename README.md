# Cloud Native Buildpack for C and C++ with Meson
[![Build and push](https://github.com/binary-craft/mesonpack/actions/workflows/build-and-push.yml/badge.svg)](https://github.com/binary-craft/mesonpack/actions/workflows/build-and-push.yml)

## About
This project is used to create a Cloud Native Buildpack for Meson that can be used for native applications such as C and C++.

## Using the buildpack
The published buildpack will be made available on Docker hub. This project contains the source and is used to build it.

See [Docker hub](https://hub.docker.com/r/bincraft/mesonpack).

```docker pull bincraft/mesonpack:<version>```

## Building images with the buildpack
There are two options for using this buildpack:
- Using a builder image that includes it, for example [binary-craft/hera-builder](https://github.com/binary-craft/hera-builder).
- Adding it directly on the commandline, this can be done like follows:

```pack build my-app -b bincraft/mesonpack:<version>```

### Arguments to pass to the build script
The buildpack has some environment variables / arguments that can be set to customise the build.

| Variable              | Description                        | Default value |
|-----------------------|------------------------------------|---------------|
| BP_MESON_COMPILE_ARGS | Compile arguments to pass to Meson | -             |
| BP_MESON_SETUP_ARGS   | Setup arguments to pass to Meson   | -             |
| BP_MESON_TEST_ARGS    | Test arguments to pass to Meson    | -             |

### Compiler choice
Meson will choose a default compiler depending on the environment. At the present time it is not yet possible to override this.

## Maintaining
This project is aimed to have a straightforward maintenance by using all relevant automation that we can.

## Contributing
This project is open for any contributions that you might have. Bugfixes and feature enhancements are very welcome.

If you'd like to implement a major new feature or change some fundamentals of the project please send me a DM to discuss.

## License
This project is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for the full license text.