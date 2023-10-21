# LARAVEL PROJECT
This repository is for creating a new laravel project.

# Setup
## Docker container.
1. Create the comtainers: `docker-compose build`.
2. Kick the containers: `docker-compose up -d`.

## Laravel.
1. Go into the container: `docker exec -it laravel_app bash`.
2. Install Laravel: `composer require laravel/installer`.
3. Add the composer path to the environment variables $PATH: `export PATH=/var/www/html/vendor/bin:$PATH`.
