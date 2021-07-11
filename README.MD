# PHP Composer with Docker

Pull docker image with command
```
docker pull luri/composer:latest
```


### Bash Console

```
docker run -it --rm --name phpcli -v "$PWD":/usr/src/myapp -p 8000:8000 -w /usr/src/myapp luri/composer bash
```

### Run Artisan inside docker container

```
php artisan serve --host=0.0.0.0 --port=8000
```

then acces it from [http://localhost:8000/](http://localhost:8000/)


### Run PHP from console

```
docker run -it --rm --name phpcli -v "$PWD":/usr/src/myapp -w /usr/src/myapp luri/composer php yourfile.php
```

then create bash file `php7.sh`

```
#!/bin/sh
docker run -it --rm --name phpcli -v "$PWD":/usr/src/myapp -w /usr/src/myapp luri/composer php $*
```


### Build docker

```
docker build -f Dockerfile.yml -t luri/composer .
```

### Resource

- [PHP Composer Docker Hub](https://hub.docker.com/r/luri/composer/)


