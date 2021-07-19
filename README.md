# OpenFaaS Templates powered by kevinzhow

## swift-static
This template takes the advantages of [Docker' multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/) to shrink the function's docker image size.


| Image | State |
| ------------- | ------------- | 
| [th089/swift:5.4.1-focal](https://hub.docker.com/r/th089/swift/tags?page=1&ordering=last_updated)  |  build |
| [alpine:latest](https://hub.docker.com/layers/alpine/library/alpine/latest/images/sha256-8d99168167baa6a6a0d7851b9684625df9c1455116a9601835c2127df2aaa2f5?context=explore) | run |


## usage
```
$ faas-cli template pull https://github.com/kevinzhow/openfaas-templates-kevinzhow.git
$ faas-cli new --lang swift-static <name>
```

## demo

You can deploy the `demo.yml` to see if it works on your enviroment.

```
faas-cli deploy -f https://raw.githubusercontent.com/kevinzhow/openfaas-templates-kevinzhow/master/demo.yml

echo Hello World | faas-cli invoke hello-swift
```


## requirement

| Architucture | 
| ------------- | 
| arm64  | 
| amd64 | 

This Template had tested on raspberrypi 3 with [raspios-buster-arm64-lite](https://downloads.raspberrypi.org/raspios_lite_arm64/images/raspios_lite_arm64-2021-05-28/).

*It did not work with armhf.*
