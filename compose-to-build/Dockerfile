# Hint: Saving space is critical for building image.

# pull Drupal CMS web
FROM drupal:8-apache

# clean up apt cache to save space
RUN apt-get update && apt-get install -y git \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html/themes

# for repository deployment, reduce time and space with '--single-branch' and '--depth 1'.
RUN git clone --branch 8.x-3.x --single-branch --depth 1 https://git.drupal.org/project/bootstrap.git \
    && chown -R www-data:www-data bootstrap

# change back to default working directory in case application needs a fixed starting point.
WORKDIR /var/www/html