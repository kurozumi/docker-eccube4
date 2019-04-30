Dockerfile for EC-CUBE 4.x with docker-compose
====

## What's this

Development environment for [EC-CUBE 4.x-dev](https://github.com/EC-CUBE/ec-cube).

## How to Build Image

* git clone

```bash
git clone https://github.com/kurozumi/docker-eccube4.git
```

## Example Usage

```bash
cd docker-eccube4
docker-compose run web composer create-project ec-cube/ec-cube . "4.0.x-dev" --keep-vcs
docker-compose up -d
```

Let's Access in Browser
  * Front End) ```http://localhost:8080```
  * Back End) ```http://localhost:8080/admin```
    * ID: admin / PW: password
  * MailCatcher) ```http://localhost:1080/```

### Cleanup

```bash
docker-compose stop
docker-compose rm
```

----
* This software is released under the MIT License, see LICENSE.txt.



