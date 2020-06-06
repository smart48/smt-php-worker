# Smart48 PHP Worker

This image will be used by cronjob that starts of scheduler. It needs an image to run the xrontab of and it probably could use supervisord as well. But I am looking into this all still as cronjob should restart by itself als.


## Docker Build

To build for our own Smart48 Docker Hub repository we use

```
docker build . -t smart48/smt-php-worker
```

This will build with the tag using our organization's name and name for the image.

## Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-php-worker
```