# OpenFaaS Templates powered by kevinzhow

## swift-static
This template takes the advantages of [Docker' multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/) to shrink the function's docker image size.


## usage
```
$ faas-cli template pull https://github.com/kevinzhow/openfaas-templates-kevinzhow.git
$ faas-cli new --lang swift-static <name>
```

## requirement

| Architucture | 
| ------------- | 
| arm64  | 
| amd64 | 

This Template had tested on raspberrypi 3 with [raspios-buster-arm64-lite](https://downloads.
raspberrypi.org/raspios_lite_arm64/images/raspios_lite_arm64-2021-05-28/).

*It did not work with armhf.*
