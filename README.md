# CESSDA Metadata Validator 

This repository holds all documentation about CESSDA Metadata Validator project. 

# Getting started as developer

```
#Generate the Maven site
mvn clean site docker:build

# Lauch local docker env
docker-compose -f target/docker/context/docker-compose.yml up

# Shutdown local docker env with
docker-compose -f target/docker/context/docker-compose.yml down
```
