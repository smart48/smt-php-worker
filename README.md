# Smart48 PHP Worker

This image will be used by cronjob that starts of scheduler. It needs an image to run the xrontab of and it probably could use supervisord as well. But I am looking into this all still as cronjob should restart by itself als.


## Docker Build

To build for our own Smart48 Docker Hub repository we use

```
docker build . -t smart48/smt-php-worker
```

This will build with the tag using our organization's name and name for the image.

# Test

You can test the build image using:

```
docker run --name smt-php-worker -d smart48/smt-php-worker:latest
```
And then you can check it using

```
docker exec -it smt-php-worker ash 
/etc/supervisor/conf.d # ls -la
total 20
drwxr-xr-x    1 root     root          4096 Jun  6 05:05 .
drwxr-xr-x    1 root     root          4096 Jun  6 04:49 ..
-rw-r--r--    1 root     root           550 Jun  6 05:05 supervisord.log
-rw-r--r--    1 root     root             2 Jun  6 05:05 supervisord.pid
```

## Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-php-worker
```