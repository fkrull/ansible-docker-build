# docker-build
This role copies a Docker build context and builds the image.

## Requirements
The target host needs to have Docker installed.

## Role Variables

### Required Variables
* `build_context` *string* - path to the build context directory on the local
  system.
* `image_tags` *list of strings* - list of tags to tag image with.

### Optional Variables
* `docker_cmd` *string* - path to the docker binary, defaults to
  `/usr/bin/docker`.
* `extra_build_options` *list of strings* - extra arguments to pass to
  `docker build`.
* `build_args` *list of strings* - strings of the form `name=value` to pass to
  `docker build` as extra build arguments.
* `pull` *boolean* - whether to always attempt to pull a newer version of the
  base image; defaults to false.

## Example
    - role: docker-build
      build_context: docker/my-image
      build_args:
        - BUILD_ARG=value
      image_tags:
        - my-image:latest
        - my-image:2.1

## License
This software is licensed under the 2-clause BSD license. See the accompanying
`LICENSE.md` file.
Copyright (c) 2017, Felix Krull. All rights reserved.
