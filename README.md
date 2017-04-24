# Supported tags and respective `Dockerfile` links

- `latest` [(Dockerfile)](https://github.com/machine-data/docker-r-studio/blob/master/Dockerfile)

# R-Studio Server on Docker

This repository holds a build definition and supporting files for building a Docker image to run [R-Studio Server](https://www.rstudio.org).
It is published as automated build `machine-data/docker-r-studio` on [Docker Hub](https://registry.hub.docker.com/u/machinedata/r-studio/).

## What is R-Studio?

[R-Studio Server](https://www.rstudio.org) is an open source (AGPL v3.0 licensed) integrated development environment (IDE) for R. It includes a console, syntax-highlighting editor that supports direct code execution, as well as tools for plotting, history, debugging and workspace management. R-Studio Server is a web based frontend.

## Yet another R-Studio container?

Not quite:
- Added dependencies: Java, rJava, ggplot2, tidyr, reshape2, dplyr, DAAG, bit64, zoo, sqldf, RJDBC.
- All user data under `/home/rstudio/projects` - ready-to mount.

## Quickstart

Start R-Studio and name the container `r-studio_test`:

```sh
$ docker run -d \
    --name r-studio_test \
    --publish 8787:8787 \
    --volume $(pwd)/rstudio:/home/rstudio \
    machine-data/r-studio
```

Connect to the web interface with port 8787 and login with rstudio:rstudio

## Volumes

- `/home/rstudio`: Path where R-Studio Projects and R persistent data are saved (.rstudio).

## Ports

- `8787`: Port for the web interface

## Legal

R-Studio is written and maintained by [R-Studio](https://www.rstudio.com/about/eula/) and is [licensed](https://github.com/rstudio/rstudio/blob/master/COPYING) under the AGPL v3.0.

## Contributing

Thanks for considering contributing to docker-r-studio!
The easiest way to contribute is either by filing an [issue on Github](https://github.com/machine-data/docker-r-studio/issues) or to [fork the repository](https://github.com/machine-data/docker-r-studio/fork) to create a pull request.

If you have any questions don't hesitate to join us on Slack.
