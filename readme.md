Looking for the repository of the Open Social distribution? [Click here](https://github.com/goalgorilla/open_social)

# Open Social Developer Repository #
Repository for developers working on the Open Social distribution. This repository contains a useful development workflow in Docker for the Open Social distribution. The development takes place [here](https://github.com/goalgorilla/open_social).

Check [drupal.org](https://www.drupal.org/project/social) for more information about Open Social.
For day to day technical documentation use the [Github Wiki](https://github.com/goalgorilla/drupal_social/wiki).

Useful links for developers:
- [Roadmap]( https://www.drupal.org/node/2766871)
- [Hifi styleguide and prototype](http://styleguide.getopensocial.com/)
- [Travis CI](https://travis-ci.org/goalgorilla/drupal_social/builds)
- [Docker Hub](https://hub.docker.com/r/goalgorilla/open_social_docker/)
- [Drupal.org project page](https://drupal.org/project/social)
- [Open Social Distribution Github repo](https://github.com/goalgorilla/open_social)
- [Open Social Distribution issue queue](https://www.drupal.org/project/issues/social).
- [Composer template](https://github.com/goalgorilla/social_template)

# Installation #

### Install from project page on drupal.org ###

Visit our drupal.org [project page](https://www.drupal.org/project/social) and head to the "Installation instruction" section on the middle of the page.

### Install in Docker containers ###

1. Copy and rename the `.env.dist` to `.env` and update the .env variables, if you don't want to use the defaults. We recommend to use the `.localhost` domain extension for the `PROJECT_BASE_URL`; so that you don't have to update your host file.

2. Run the nginx-proxy container, you only need one even if you have multiple projects.
```
docker compose -f docker-compose.nginx.yml -p nginx up -d
```
3. Run the docker containers for the project:
```
docker compose up -d
```
4. Depending on the configured `PROJECT_BASE_URL`, you can access the following services:
- Drupal: http://social.localhost
- Solr: http://solr.social.localhost
- Mailcatcher: http://mailcatcher.social.localhost

5. Alternatively you can use some extra composer commands to facilitate:
- docker-up: Start all the docker containers for this project
- docker-stop: Stop the docker containers for this project. Does not stop the nginx containers
- docker-shell: Open bash within the web comtainer
- install-open-social: (Re)install Open Social using the install script
- phpstan ( inside web container ): Analyse the code in this repository using the configuration from the distribution
- phpcs ( inside web container ): Lint the code in the repository using PHP CodeSniffer with the configuration from the distribution
- phpunit ( inside web container ): Run PHPUnit tests in this project with the configuration from the distribution

### Install with Composer ###

Checkout this repository for a Composer template: [goalgorilla/social_template](https://github.com/goalgorilla/social_template).

# Contribute #
Contribute to Open Social? Checkout our [Contribution to Open Social](https://github.com/goalgorilla/drupal_social/wiki/Contributing-to-Open-Social) section on out github wiki

Do you want to join us in this effort? We are welcoming your [feedback](http://goalgorilla.github.io/drupal_social/prototype.html), (development) time and/or financial support. For feedback, questions or suggestions you can use [Drupal.org](https://www.drupal.org/project/social).

If you find any issues feel free to file a bug report in the [issue queue](https://www.drupal.org/project/issues/social).

[![Build Status Drupal Social](https://travis-ci.org/goalgorilla/drupal_social.svg?branch=master)](https://travis-ci.org/goalgorilla/drupal_social)
[![Build Status Open Social](https://api.travis-ci.org/goalgorilla/open_social.svg?branch=8.x-1.x)](https://travis-ci.org/goalgorilla/open_social)

