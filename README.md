# docker-ipt
A docker image for the [GBIF IPT](https://github.com/gbif/ipt) running in Tomcat with JRE8.
Tomcat is exposed on port 8080 and the IPT runs as the ROOT application.

## Build docker image

```docker build -t sibbr/ipt .```

## Run docker image locally
To run a new docker container, startup tomcat and expose the tomcat port run this:

```docker run --rm -v /hostDataDir:/usr/local/ipt -v /hostLogsDir:/usr/local/tomcat/logs -p 80:8080 sibbr/ipt```

```-v``` option is used when you want to store/share data between host:guest. This case we're sharing IPT datadir and tomcat logs with host.

```--rm``` will remove the container when halted, you can switch to ```-d``` to detach/restore later.

```-p``` choose with host:guest ports to publish.

## Setup

At Setup 2 when first accessing IPT you must enter your "public" available IP[:PORT] on base URL. Ex. http://10.179.188.236:8080
