# CESSDA Metadata Validator 

This repository holds all documentation about CESSDA Metadata Validator project. 

### Getting started as developer

```shell
# Pull repository and change directory
git clone git@bitbucket.org:cessda/cessda.cmv.git
cd cessda.cmv

# Generate the Maven site
mvn clean site docker:build

# Lauch local docker env
docker-compose -f target/docker/context/docker-compose.yml up

# Open your browser
xdg-open http://localhost:80

# Shutdown local docker env with
docker-compose -f target/docker/context/docker-compose.yml down
```
