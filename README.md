# Docker Registry

To be used as submodule to other compose projects to provide local docker registry

The docker-compose.registry.yml in this submodule contains 3 registries:

- `registry`: used to store images built by CI
- `docker-hub`: mirror of docker hub, to speed up downloading of public images from docker hub
- `mcr`: mirror of Microsoft container registry (MCR), to speed up downloading of .NET related docker images

## Usage (in other compose projects)

```
git submodule add https://github.com/hpcsc/registry
git submodule update --init
```

This registry submodule expects parent project to provide 1 environment variable `REGISTRY_VERSION`

When using with parent project, `docker-compose.registry.yml` needs to be passed in explicitly to docker-compose command (or set `COMPOSE_FILE` variable)

## Examples of usage

- [https://github.com/hpcsc/teamcity](https://github.com/hpcsc/teamcity)
