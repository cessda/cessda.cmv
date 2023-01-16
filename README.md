[![SQA badge](https://api.eu.badgr.io/public/assertions/SyOB9h-fSeq04OYVOQaNPw/image)](https://api.eu.badgr.io/public/badges/IDUsZJpNQPuiJpPwmJ8iJw)

[![Build Status](https://jenkins.cessda.eu/buildStatus/icon?job=cessda.cmv%2Fmain)](https://jenkins.cessda.eu/job/cessda.cmv/job/main/)
[![Bugs](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=bugs)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Code Smells](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=code_smells)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Coverage](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=coverage)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Duplicated Lines (%)](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=duplicated_lines_density)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Lines of Code](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=ncloc)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Maintainability Rating](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=sqale_rating)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Quality Gate Status](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=alert_status)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Reliability Rating](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=reliability_rating)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Security Rating](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=security_rating)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Technical Debt](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=sqale_index)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)
[![Vulnerabilities](https://sonarqube.cessda.eu/api/project_badges/measure?project=eu.cessda.cmv%3Acmv&metric=vulnerabilities)](https://sonarqube.cessda.eu/dashboard?id=eu.cessda.cmv%3Acmv)

# CESSDA Metadata Validator

This repository holds all documentation about CESSDA Metadata Validator project.

## Getting started as developer

```shell
# Pull repository and change directory
git clone https://github.com/cessda/cessda.cmv.git
cd cessda.cmv

# Generate the Maven site
./mvnw clean site docker:build

# Lauch local docker env
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

You can find the list of changes made in each release in the [CHANGELOG](CHANGELOG.md) file.

## License

See the [LICENSE](LICENSE.txt) file.

## Citing

See the [CITATION](CITATION.cff) file.
