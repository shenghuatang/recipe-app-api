# Recipe App API

Source code for my Udemy course Build a [Backend REST API with Python & Django - Advanced](http://udemy.com/django-python-advanced/).

The course teaches how to build a fully functioning REST API using:

 - Python
 - Django / Django-REST-Framework
 - Docker / Docker-Compose
 - Test Driven Development

## Getting started

To start project, run:

```
docker-compose up
```

The API will then be available at http://127.0.0.1:8000




https://github.com/shenghuatang/recipe-app-api.git

# my installation
`
(base) ubuntu@frank-lenovo:~/recipe-app-api$ sudo docker-compose build
db uses an image, skipping
Building app
Step 1/17 : FROM python:3.7-alpine
3.7-alpine: Pulling from library/python
df20fa9351a1: Pull complete
36b3adc4ff6f: Pull complete
ae9c05960bd7: Pull complete
7442392bb9e7: Pull complete
f6327682c96d: Pull complete
Digest: sha256:ff279505f12ad2226679737a583bd93b361a768aa94d20ff4a668bfecc34608d
Status: Downloaded newer image for python:3.7-alpine
 ---> 4fac8cece98e
Step 2/17 : MAINTAINER London App Developer Ltd
 ---> Running in efd2f518eb88
Removing intermediate container efd2f518eb88
 ---> aa5d7066a244
Step 3/17 : ENV PYTHONUNBUFFERED 1
 ---> Running in 4232447e28da
Removing intermediate container 4232447e28da
 ---> 0379ed5ffcf8
Step 4/17 : COPY ./requirements.txt /requirements.txt
 ---> 158055cab94c
Step 5/17 : RUN apk add --update --no-cache postgresql-client jpeg-dev
 ---> Running in 356e2df5313e
fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/community/x86_64/APKINDEX.tar.gz
(1/10) Installing libjpeg-turbo (2.0.5-r0)
(2/10) Installing pkgconf (1.7.2-r0)
(3/10) Installing libjpeg-turbo-dev (2.0.5-r0)
(4/10) Installing jpeg-dev (9d-r0)
(5/10) Installing libedit (20191231.3.1-r0)
(6/10) Installing db (5.3.28-r1)
(7/10) Installing libsasl (2.1.27-r6)
(8/10) Installing libldap (2.4.50-r0)
(9/10) Installing libpq (12.3-r2)
(10/10) Installing postgresql-client (12.3-r2)
Executing busybox-1.31.1-r16.trigger
OK: 17 MiB in 45 packages
Removing intermediate container 356e2df5313e
 ---> 4e9c76d8f5a7
Step 6/17 : RUN apk add --update --no-cache --virtual .tmp-build-deps       gcc libc-dev linux-headers postgresql-dev musl-dev zlib zlib-dev
 ---> Running in 328f398dab62
fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/community/x86_64/APKINDEX.tar.gz
(1/27) Installing libgcc (9.3.0-r2)
(2/27) Installing libstdc++ (9.3.0-r2)
(3/27) Installing binutils (2.34-r1)
(4/27) Installing gmp (6.2.0-r0)
(5/27) Installing isl (0.18-r0)
(6/27) Installing libgomp (9.3.0-r2)
(7/27) Installing libatomic (9.3.0-r2)
(8/27) Installing libgphobos (9.3.0-r2)
(9/27) Installing mpfr4 (4.0.2-r4)
(10/27) Installing mpc1 (1.1.0-r1)
(11/27) Installing gcc (9.3.0-r2)
(12/27) Installing musl-dev (1.1.24-r9)
(13/27) Installing libc-dev (0.7.2-r3)
(14/27) Installing linux-headers (5.4.5-r1)
(15/27) Installing libxml2 (2.9.10-r4)
(16/27) Installing llvm10-libs (10.0.0-r2)
(17/27) Installing clang-libs (10.0.0-r2)
(18/27) Installing clang (10.0.0-r2)
(19/27) Installing llvm10 (10.0.0-r2)
(20/27) Installing openssl-dev (1.1.1g-r0)
(21/27) Installing icu-libs (67.1-r0)
(22/27) Installing icu (67.1-r0)
(23/27) Installing icu-dev (67.1-r0)
(24/27) Installing postgresql-libs (12.3-r2)
(25/27) Installing postgresql-dev (12.3-r2)
(26/27) Installing zlib-dev (1.2.11-r3)
(27/27) Installing .tmp-build-deps (20200813.153716)
Executing busybox-1.31.1-r16.trigger
OK: 365 MiB in 72 packages
Removing intermediate container 328f398dab62
 ---> 66ea899fd634
Step 7/17 : RUN pip install -r /requirements.txt
 ---> Running in cb801b61e4d4
Collecting Django<2.2.0,>=2.1.3
  Downloading Django-2.1.15-py3-none-any.whl (7.3 MB)
Collecting djangorestframework<3.10.0,>=3.9.0
  Downloading djangorestframework-3.9.4-py2.py3-none-any.whl (911 kB)
Collecting psycopg2<2.8.0,>=2.7.5
  Downloading psycopg2-2.7.7.tar.gz (427 kB)
Collecting Pillow<5.4.0,>=5.3.0
  Downloading Pillow-5.3.0.tar.gz (15.6 MB)
Collecting flake8<3.7.0,>=3.6.0
  Downloading flake8-3.6.0-py2.py3-none-any.whl (68 kB)
Collecting pytz
  Downloading pytz-2020.1-py2.py3-none-any.whl (510 kB)
Collecting mccabe<0.7.0,>=0.6.0
  Downloading mccabe-0.6.1-py2.py3-none-any.whl (8.6 kB)
Collecting pyflakes<2.1.0,>=2.0.0
  Downloading pyflakes-2.0.0-py2.py3-none-any.whl (53 kB)
Requirement already satisfied: setuptools>=30 in /usr/local/lib/python3.7/site-packages (from flake8<3.7.0,>=3.6.0->-r /requirements.txt (line 6)) (49.3.1)
Collecting pycodestyle<2.5.0,>=2.4.0
  Downloading pycodestyle-2.4.0-py2.py3-none-any.whl (62 kB)
Building wheels for collected packages: psycopg2, Pillow
  Building wheel for psycopg2 (setup.py): started
  Building wheel for psycopg2 (setup.py): still running...
  Building wheel for psycopg2 (setup.py): finished with status 'done'
  Created wheel for psycopg2: filename=psycopg2-2.7.7-cp37-cp37m-linux_x86_64.whl size=224735 sha256=f569dae859debca893bf961f7d94a7f2ac576b78dd66e7196daa091a1891fb6f
  Stored in directory: /root/.cache/pip/wheels/3d/c8/cd/d43fc1edb0127f01f4dee6789fd45d8e93e211e0fd9a04b824
  Building wheel for Pillow (setup.py): started
  Building wheel for Pillow (setup.py): still running...
  Building wheel for Pillow (setup.py): finished with status 'done'
  Created wheel for Pillow: filename=Pillow-5.3.0-cp37-cp37m-linux_x86_64.whl size=491735 sha256=8bfbefdae11361f9b80b1f5aa37cd607115d970d0f79d9b157685bd4ec8d7634
  Stored in directory: /root/.cache/pip/wheels/37/1c/ef/a8aa77ac404747027e681948bc0a8925b96e96f8caa36cb00d
Successfully built psycopg2 Pillow
Installing collected packages: pytz, Django, djangorestframework, psycopg2, Pillow, mccabe, pyflakes, pycodestyle, flake8
Successfully installed Django-2.1.15 Pillow-5.3.0 djangorestframework-3.9.4 flake8-3.6.0 mccabe-0.6.1 psycopg2-2.7.7 pycodestyle-2.4.0 pyflakes-2.0.0 pytz-2020.1
Removing intermediate container cb801b61e4d4
 ---> 70e7c1ee91f2
Step 8/17 : RUN apk del .tmp-build-deps
 ---> Running in 2cc6ea8fa0fe
WARNING: Ignoring APKINDEX.2c4ac24e.tar.gz: No such file or directory
WARNING: (1/27) Purging .tmp-build-deps (20200813.153716)
(2/27) Purging gcc (9.3.0-r2)
Ignoring APKINDEX.40a3604f.tar.gz: No such file or directory
(3/27) Purging binutils (2.34-r1)
(4/27) Purging libatomic (9.3.0-r2)
(5/27) Purging libgomp (9.3.0-r2)
(6/27) Purging libgphobos (9.3.0-r2)
(7/27) Purging libc-dev (0.7.2-r3)
(8/27) Purging linux-headers (5.4.5-r1)
(9/27) Purging postgresql-dev (12.3-r2)
(10/27) Purging clang (10.0.0-r2)
(11/27) Purging openssl-dev (1.1.1g-r0)
(12/27) Purging icu-dev (67.1-r0)
(13/27) Purging icu (67.1-r0)
(14/27) Purging icu-libs (67.1-r0)
(15/27) Purging postgresql-libs (12.3-r2)
(16/27) Purging musl-dev (1.1.24-r9)
(17/27) Purging zlib-dev (1.2.11-r3)
(18/27) Purging llvm10 (10.0.0-r2)
(19/27) Purging clang-libs (10.0.0-r2)
(20/27) Purging llvm10-libs (10.0.0-r2)
(21/27) Purging libstdc++ (9.3.0-r2)
(22/27) Purging libgcc (9.3.0-r2)
(23/27) Purging isl (0.18-r0)
(24/27) Purging mpc1 (1.1.0-r1)
(25/27) Purging mpfr4 (4.0.2-r4)
(26/27) Purging gmp (6.2.0-r0)
(27/27) Purging libxml2 (2.9.10-r4)
Executing busybox-1.31.1-r16.trigger
OK: 17 MiB in 45 packages
Removing intermediate container 2cc6ea8fa0fe
 ---> db0ece3069ca
Step 9/17 : RUN mkdir /app
 ---> Running in 3bb96cd43716
Removing intermediate container 3bb96cd43716
 ---> dce766ad7383
Step 10/17 : WORKDIR /app
 ---> Running in cde731856966
Removing intermediate container cde731856966
 ---> e63dacb9fac4
Step 11/17 : COPY ./app /app
 ---> fc8c0856c011
Step 12/17 : RUN mkdir -p /vol/web/media
 ---> Running in b607492c0ff9
Removing intermediate container b607492c0ff9
 ---> 584e23f5c3fa
Step 13/17 : RUN mkdir -p /vol/web/static
 ---> Running in ff69380369ef
Removing intermediate container ff69380369ef
 ---> 2037009186a7
Step 14/17 : RUN adduser -D user
 ---> Running in 577745beb8eb
Removing intermediate container 577745beb8eb
 ---> 649ba71759aa
Step 15/17 : RUN chown -R user:user /vol/
 ---> Running in 4d4951fd0fa6
Removing intermediate container 4d4951fd0fa6
 ---> d915562dec53
Step 16/17 : RUN chmod -R 755 /vol/web
 ---> Running in ebeb9ef4848e
Removing intermediate container ebeb9ef4848e
 ---> a39aecfc8290
Step 17/17 : USER user
 ---> Running in 85c5ced431da
Removing intermediate container 85c5ced431da
 ---> cd738b0587c0
Successfully built cd738b0587c0
Successfully tagged recipe-app-api_app:latest
`
