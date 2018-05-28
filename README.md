# OpenHAB docker container used for development

## Description

This docker-compose script will start 2 containers:

- OpenHAB configured with the experimental rule engine (ECMAscript & Jython)
- Frontail webbased log monitoring

Frontail can be accessed on http://localhost:29001 and the OpenHAB web interface can be reached on http://localhost:18080

Note: If you run Docker on a Windows host, use [docker-windows-notifier](https://www.npmjs.com/package/docker-windows-notifier) to propagate mounted volume file system changes. (source: [inotify on shared drives does not work](https://docs.docker.com/docker-for-windows/troubleshoot/#/inotify-on-shared-drives-does-not-work))

## Usage

The bind volumes used by the containers will be mounted underneath the `./volumes` folder. This data will persist.

### Starting & stopping containers

To start both the OpenHAB container and the frontail weblog viewer, run the following command:

```
$ docker-compose up -d
```

To stop both containers, run the following command:

```
$ docker-compose down
```

### Remove containers and network bridge

To remove containers and network bridge config, run the following command:

```
$ docker-compose rm && docker network prune
```
