# OPA ( Open Policy Agent ) for Docker

This action runs/validate your Dockerfile with a set of policies and uses OPA Conftest.

There would be no need to have a policy folder within your repo.

## Input
---------------

| Property    	|  Required 	|  Description 	| 
|---	|---	|---	|
| file  	|  Yes 	|  The Dockerfile from the source repo	|
| output  	|  No 	|  Defaults to stdout 	| 


## Usage
------------------

Pull Docker file from registry

```
on:
  push: [main]
jobs:
  run-opa-docker:
    runs-on: ubuntu-latest

steps:
    - uses: actions/checkout@v2
    - name: OPA Docker
    uses: itsmesuniljacob/opa-docker@main
    with:
        file: Dockerfile
```

## Success scenario

```
Status: Downloaded newer image for openpolicyagent/conftest:latest
8 tests, 8 passed, 0 warnings, 0 failures, 0 exceptions
```

## Failure scenario
```
Status: Downloaded newer image for openpolicyagent/conftest:latest
FAIL - Dockerfile - main - Do not run as root, use USER instead
8 tests, 7 passed, 0 warnings, 1 failure, 0 exceptions
Error: Process completed with exit code 1.
```
