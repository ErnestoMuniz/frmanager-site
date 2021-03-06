---
title: Installation
excerpt: This is the installation section.
seo:
  title: Installation
  description: This is the Installation page
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Installation
      keyName: property
    - name: 'og:description'
      value: This is the Installation page
      keyName: property
    - name: 'twitter:card'
      value: summary
    - name: 'twitter:title'
      value: Installation
    - name: 'twitter:description'
      value: This is the Installation page
layout: docs
---
First of all clone the repository inside your `/var/www/` directory:

```bash
cd /var/www
git clone https://github.com/ErnestoMuniz/FreeRadiusManager.git
```

Then install the needed composer packages:

```bash
cd FreeRadiusManager/
composer update
```

Make a copy of the `.env.example` file and edit the FreeRadius database connection:

```bash
cp .env.example .env
```

```env
...
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
...
```

Generate your application key and run migrations:

```bash
php artisan key:generate
php artisan migrate:refresh --seed
```

Run the `activate.sh` script:

```bash
sh activate.sh
```

Then your installation is done, you can now proceed to the Apache configuration guide.