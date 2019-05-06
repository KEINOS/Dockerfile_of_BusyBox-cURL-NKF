[![](https://img.shields.io/docker/cloud/automated/keinos/busybox-curl-nkf.svg)](https://hub.docker.com/r/keinos/busybox-curl-nkf/builds "Docker Hub Build Status") [![](https://img.shields.io/docker/cloud/build/keinos/busybox-curl-nkf.svg)](https://hub.docker.com/r/keinos/busybox-curl-nkf/builds "Docker Hub Build Status")

# Dockerfile of BusyBox-cURL-NKF

```text
docker pull keinos/busybox-curl-nkf
```

Docker container of BusyBox with cURL and NKF (Network Kanji Filter) installed.

Useful if you want to URL-encode a string and curl (POST) it to RESTful Web APIs with `sh` shell script.

- Repositories:
  - Image: https://hub.docker.com/r/keinos/busybox-curl-nkf @ DockerHub
  - Source: https://github.com/KEINOS/Dockerfile_of_BusyBox-cURL-NKF @ GitHub

## Usage

```shellsession
$ # Pull the docker image
$ docker pull keinos/busybox-curl-nkf
...
```

### Basic Usage

```shellsession
$ # Check version of cURL
$ docker run --rm busybox-curl-nkf curl --version
curl 7.39.0 (x86_64-buildroot-linux-gnu) libcurl/7.39.0 OpenSSL/1.0.1j zlib/1.2.8 libssh2/1.4.3
Protocols: dict file ftp ftps gopher http https imap imaps pop3 pop3s rtsp scp sftp smtp smtps telnet tftp
Features: IPv6 Largefile NTLM SSL libz TLS-SRP
$
$ # Check version of NKF
$ docker run --rm busybox-curl-nkf nkf --version
Network Kanji Filter Version 2.1.5 (2018-12-15)
Copyright (C) 1987, FUJITSU LTD. (I.Ichikawa).
Copyright (C) 1996-2018, The nkf Project.
```

## Build your own

If you don't want to pull the built image but build it your own, then just get the Dockerfile and build it.

- Get Dockerfile:
  - Download: https://KEINOS.github.io/Dockerfile_of_BusyBox-cURL-NKF/Dockerfile
  - View: https://github.com/KEINOS/Dockerfile_of_BusyBox-cURL-NKF/blob/master/Dockerfile
  - Clone: https://github.com/KEINOS/Dockerfile_of_BusyBox-cURL-NKF.git

```shellsession
$ # Create and move to work directory
$ mkdir my_busybox_curl_nkf && cd $_
$ # Get the Dockerfile (cURL for example)
$ curl -LO https://KEINOS.github.io/Dockerfile_of_BusyBox-cURL-NKF/Dockerfile
...
$ ls
Dockerfile
$ # Build
$ docker build --tag busybox-curl-nkf .
...
$ # Check version of NKF
$ docker run --rm busybox-curl-nkf nkf --version
Network Kanji Filter Version 2.1.5 (2018-12-15)
Copyright (C) 1987, FUJITSU LTD. (I.Ichikawa).
Copyright (C) 1996-2018, The nkf Project.
```

## Tested env

```shelsession
$ # Host OS info (macOS)
$ sw_vers
ProductName:    Mac OS X
ProductVersion: 10.14.4
BuildVersion:   18E226
$
$ docker version
Client: Docker Engine - Community
 Version:           18.09.0
 API version:       1.39
 Go version:        go1.10.4
 Git commit:        4d60db4
 Built:             Wed Nov  7 00:47:43 2018
 OS/Arch:           darwin/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.0
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.4
  Git commit:       4d60db4
  Built:            Wed Nov  7 00:55:00 2018
  OS/Arch:          linux/amd64
  Experimental:     false
```
