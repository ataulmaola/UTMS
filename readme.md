# Welcome to UTMS!

## Overview


UTMS is a powerful, consistent, and flexible thesis management system. Built upon the laravel framework, UTMS provides a simple yet highly extensible architecture that encourages diving in and hacking on the code. 

![utms](https://user-images.githubusercontent.com/17488819/50128107-01374b00-029e-11e9-83cc-2edee96f69c1.png)
      
More [screenshots](screenshots.md).

* [System requirements](#system-requirements)
* [Features](#features)
* [How To Use](#how-to-use)
* [Updating](#updating)
* [Credits](#Credits)
* [Documentation](#documentation)
* [License](#license)

## System requirements

* PHP 7 (with Laravel Framework);

* Web-server (Nginx or Apache2);

* Unix-like OS (**Windows isn't supported**);

* Database (MySQL);

* Frondend(Bootstrap,Javascript)

## Features

* Student Panel(Student dashboard,Profile,Email,Message);

* Teacher Panel(Dashboard,Profile);

* Thesis/Project Member-Group Create;

* Set up and tear down database tests for  MySQL ;

* Interactive Super Admin



## How To Use

* Go to the directory in which you want to install PHP Censor, for example: `/var/www`:

```bash
cd /var/www
```



## Updating

* Go to your PHP Censor directory (to `/var/www/php-censor.local` for example):

    ```bash
    cd /var/www/php-censor.local
    ```

* Pull the latest code from repository by Git (If you want latest `master` branch):

    ```bash
    git checkout master
    git pull -r
    ```

    Or pull latest version:

    ```bash
    git fetch
    git checkout <version>
    ```

* Update the Composer dependencies: `composer install`

* Update the database scheme:

    ```bash
    ./bin/console php-censor-migrations:migrate
    ```

* Restart Supervisord workers (If you use workers and Supervisord):

    ```bash
    sudo supervisorctl status
    sudo supervisorctl restart <worker:worker_00>
    ...
    sudo supervisorctl restart <worker:worker_nn>
    ```
    
    Or restart Systemd workers (If you use workers and Systemd):
    
    ```bash
    sudo systemctl restart <worker@1.service>
    ...
    sudo systemctl restart <worker@n.service>
    ```



## Credits

```bash
cd /path/to/php-censor

./vendor/bin/phpunit --configuration ./phpunit.xml --coverage-html ./tests/runtime/coverage -vvv --colors=always
```

For Phar plugin tests set 'phar.readonly' setting to Off (0) in `php.ini` config. Otherwise tests will be skipped.  

For database B8Framework tests create empty 'b8_test' database on 'localhost' with user/password: `root/<empty>` 
for MySQL and with user/password: `postgres/<empty>` for PostgreSQL (You can change default test user, password and 
database name in `phpunit.xml` config constants). If connection failed tests will be skipped.

## Documentation

[Full PHP Censor documentation](docs/en/README.md).

## License

PHP Censor is open source software licensed under the [BSD-2-Clause license](LICENSE).
