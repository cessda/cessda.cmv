[![Build Status](https://jenkins.cessda.eu/buildStatus/icon?job=cessda.cmv%2Fmain)](https://jenkins.cessda.eu/job/cessda.cmv/job/main/)

# CESSDA Metadata Validator

This repository holds all documentation about CESSDA Metadata Validator project.

## Getting started as developer

```shell
# Pull repository and change directory
git clone https://github.com/cessda/cessda.cmv.git
cd cessda.cmv

# Generate the Maven site
./mvnw clean site docker:build

# Launch local docker env
docker-compose -f target/docker/context/docker-compose.yml up

# Open your browser
xdg-open http://localhost:80

# Shutdown local docker env with
docker-compose -f target/docker/context/docker-compose.yml down
```

## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) for details on our code of conduct,
and the process for submitting pull requests to us.

## Versioning

See [Semantic Versioning](https://semver.org/) for guidance.

## Changes

You can find the list of changes made in each release in the
[CHANGELOG](CHANGELOG.md) file.

## License

See the [LICENSE](LICENSE.txt) file.

## Citing

See the [CITATION](CITATION.cff) file.
