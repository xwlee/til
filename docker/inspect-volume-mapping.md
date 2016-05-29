You can inspect your mount mapping with the Docker `inspect` command.

Mount host volume into a container:
```shell
$ docker run -it -v "$PWD":/data ubuntu:14.04 /bin/bash
root@44d71a605b5b:/#

# { ..., "RW": true, "Propagation": "rprivate" }
$ docker inspect -f {{.Mounts}} 44d71a605b5b 
[{ /home/vagrant/data /data   true rprivate}]
```

Create a new volume inside a container:
```shell
$ docker run -ti -v /cookbook ubuntu:14.04 /bin/bash
root@34e7ef4dd55a:/#

# { ..., "Driver": "local", "RW": true }
$ docker inspect -f {{.Mounts}} 34e7ef4dd55a
[{513d288ce950b078c92da2da277a4f79ce8b0aa9cbf75e230a51149d65a4b669 /var/lib/docker/volumes/513d288ce950b078c92da2da277a4f79ce8b0aa9cbf75e230a51149d65a4b669/_data /cookbook local  true }]
```
