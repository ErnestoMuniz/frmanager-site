---
title: Apache Configuration
excerpt: >-
  In this section you'll learn how to add syntax highlighting, examples,
  callouts and much more.
seo:
  title: Apache Configuration
  description: This is the Apache Configuration page
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Apache Configuration
      keyName: property
    - name: 'og:description'
      value: This is the Apache Configuration page
      keyName: property
    - name: 'twitter:card'
      value: summary
    - name: 'twitter:title'
      value: Apache Configuration
    - name: 'twitter:description'
      value: This is the Apache Configuration page
layout: docs
---

First you will need to create the `frmanager.cong` file inside your `/etc/apache2/sites-available/` folder:

After that edit the following configuration file according to your needs and put it in yout `frmanager.conf` file:

```html
<VirtualHost \*:80>
ServerAdmin webmaster@localhost
ServerName frmanager.local
DocumentRoot /var/www/FreeRadiusManager/public

    <Directory "/var/www/FreeRadiusManager/public">
            Options FollowSymLinks MultiViews
            Order Allow,Deny
            Allow from all
            AllowOverride All
            ReWriteEngine On
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>
```

Then you must enable Apache Rewrite Module with:

```bash
sudo a2enmod rewrite
```

Now your frManager should be ready to use =D