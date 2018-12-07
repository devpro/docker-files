# Symfony

## Run the example

composer require server --dev

## Steps to reproduce

### Pre-requisite

- Docker

- git

- PHP / Composer

```bash
sudo apt update
sudo apt install curl php-cli php-mbstring unzip php-curl php-xml php-zip
sudo apt-get install php-curl
php -v
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
composer -V
```

See. [digitalocean tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-18-04)

### Symfony project

- Use Composer to create the project from a skeleton

```bash
composer create-project symfony/website-skeleton sf4-website
```

- You can try locally the site with `composer require server --dev` and run the unit tests with `php bin/phpunit`.
