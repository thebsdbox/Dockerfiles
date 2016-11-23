# Dockerfiles PI
Dockerfiles for the Raspberry Pi 


# Building InfraKit on the rPI
This is a relatively straight forward set of actions, consisting of two steps.
1. Build an image with the golang binaries
2. Use your new image to build the InfraKit binareies

## Build goarm image
Download the goarm Dockerfile from above and the golang binaries from https://golang.org/dl/ in particular go1.7.3.linux-armv6l.tar.gz, to the location where your Dockerfile has been downloaded too (if you use a newer binary archive then tweak the goarm Dockerfile accordingly.
```$ docker build -t goarm .
```

## Build InfraKit
Download the InfraKit arm Dockerfile from above and do a Docker build
`$ docker build -t infrakit-arm .`

## Deploy infrastructure from a Raspberry Pi
` $ docker run -it infrakit-arm bash`
...
```
$ build/infrakit
infrakit cli

Usage:
  build/infrakit [command]

Available Commands:
  flavor      Access flavor plugin
  group       Access group plugin
  instance    Access instance plugin
  plugin      Manage plugins
  version     print build version information

{ ... }

$ uname -a
Linux aec757bc752a 4.4.13-v7+ #894 SMP Mon Jun 13 13:13:27 BST 2016 armv7l GNU/Linux
```

## Notes!
This was only to see how difficult the procedure would be, the Dockerfiles can be written much more efficently.
