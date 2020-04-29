# Introduction

Practice for Docker Compose to build. Building a customized Drupal CMS web (add a "Bootstrap" option in Appearance --> Uninstalled themes) and a Postgres DB during `docker-compose up`.

# Detail

* Dockerfile
  * pull drupal:8-apache
  * update apt, install git and clean apt cache.
  * change working directory to `/var/www/html/themes`
  * `git clone` bootstrap repo with only one branch, and with a history truncated to 1.
  * recover working directory in case

* docker-compose.yml
  * assign a custom name for Drupal being built
  * specify build info for Drupal

# Usage

```
// run containers and build image(s) if not found in cache
docker-compose up

// rebuild image(s)
docker-compose build
// or specify a explicit `--build`, the old image name and tag would both become: <none>
docker-compose up --build


// tear down containers
docker-compose down

// tear down containers and volumes
docker-compose down -v

```

# Tips

* Dockerfile
  * Saving space is critical for building image (clean up cache, pull necessary data only).
* docker-compose.yml
  * The `image` attribute of a service usually indicates the image name it would try to pull from Ducker Hub. However, if `image`, `build` attributes appears altogether, it would use the image name to write to in our image cache.
  * The `build` attribute can ba either a string for building path, or can extend to specify: building path, building file, arguments.
