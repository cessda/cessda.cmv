# cessda.cmv - CESSDA Metadata Validator 

This repository holds all documentation about CESSDA Metadata Validator project. 

* Generate the Maven site with
	```bash
	mvn clean site docker:build
	```
	
* Lauch local docker env with
	```bash
	docker-compose -f target/docker/context/docker-compose.yml up
	```
	
* Shutdown local docker env with
	```bash
	docker-compose -f target/docker/context/docker-compose.yml down
	```
	