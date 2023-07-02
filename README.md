# Where abouts App

An app to track peoples where abouts. Built with Quasar.

**Getting started**

This repository has been set up to work with docker compose. You need docker
and docker compose to use the commands below.

```
# copy docker-compose.override and customize as needed
cp docker-compose.override-sample.yml docker-compose.override.yml

# start the containers
docker compose up -d

# install composer packages
docker compose exec php sh
cd drupal
composer install

# initialise drupal
composer build
```

Once installed you can access the dev site
where.docker.localhost:8000

Drupal backend
api.where.docker.localhost:8000

## Resources

* [Quasar](https://quasar.dev/)
* [Drupal 9](https://www.drupal.org/project/drupal/)
* [Github Project](https://github.com/ainsofs/where-abouts)

**Common commands**

```
# start up dev environment
docker-compose up -d

# stop environment
docker-compose stop

# delete everything and start in a clean environment
docker-compose down -v

# check logs
docker-compose logs -f

# check logs for specific container
docker-compose logs -f quasar

# log into node container (this will allow use of drush and composer)
docker-compose exec quasar sh

```

**Tips**

Use aliases

```
# docker compose aliases
alias dc="docker compose"
alias dup="docker compose up -d"
alias dlup="docker compose up -d && docker compose logs php"
alias dphp="docker compose exec php sh"
alias dnode="docker compose exec node bash"
alias dquasar="docker compose exec quasar bash"
alias dstop="docker compose stop"

# git aliases
alias gc="git add . && git commit -m"
alias gpush="git push origin"
alias gf="git fetch origin"
alias gp="git fetch --prune"
```
