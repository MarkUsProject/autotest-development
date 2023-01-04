# Autotest Development

This repository contains submodules of all the autotesting related repositories needed to run the autotester.

This is meant to facilitate development of these submodules since this module includes a docker-compose.yml file which creates a development environment in docker for each of the backends with all of the testers and plugins installed.

For example, to start the classic autotester backend and api:

```
docker compose up backend_classic
```

to start the docker autotester backend and api:

```
docker compose up backend_docker
```

to start the api by itself without any backend:

```
docker compose up api
```

The api will accept http requests over the `markus_dev` network at `autotest-api:5000`.


If you create a new backend, plugin, or tester make sure to add it as a submodule to this repository:

- new backends should be added in the repository root (and add a new service to the docker-compose.yml file)
- new testers should be added in the testers/ subdirectory
- new plugins should be added in the plugins/ subdirectory
