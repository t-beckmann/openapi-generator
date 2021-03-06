# openapi_server Swagger-ui and Resource Types

This project is an autogenerated microservice for Ciena's Blueplanet platform.

## Overview

Generated code can be used as:

* Resource Type generation for Resource Adapter Development
* Resource Type generation for Service Template Development
* Microservice for swagger based NBI

Make Targets:

image: Create Docker image for use as BluePlanet microservice
solution: Create Solution image

Resource Types are generated in model-definitions directory

## Usage

### Creating new release

1. Update RELEASE property in Makefile
2. Update release(s) in [fig.yml](solution/fig.yml)
3. make image and solution

    ```bash
    # building the image
    make image
    make solution
    ```

### Iterative Development

1. A helper target can be used for pushing image and solution to server

    ```bash
    make update REMOTE_SERVER=bpadmin@10.10.10.10
    ```

This `make` target does the following:

1. creates App and Solution image
2. purges solution from MCP remote
3. pushes solution and image to MCP remote
4. deploys solution

### Local Usage

To run the server locally:

```bash
cd app
pip3 install -r requirements.txt
python3 -m swagger_server
```

and open your browser to [here](http://localhost:8080/openapi_server/ui/)
