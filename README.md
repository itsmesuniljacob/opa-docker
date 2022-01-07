# OPA ( Open Policy Agent ) for Docker

This action runs/validate your Dockerfile with a set of policies and used OPA Conftest.

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

## Success Scenario

