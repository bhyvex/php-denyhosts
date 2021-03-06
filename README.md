PhpDenyhosts
============

[![Build Status](https://travis-ci.org/zwiazeksyndykalistowpolski/php-denyhosts.svg?branch=master)](https://travis-ci.org/zwiazeksyndykalistowpolski/php-denyhosts)

Inspired by the _denyhosts_ and _fail2ban_ projects created **to secure cheap shared hostings** where is no
access to the shell, but there is still an **access.log** and **Apache htaccess** accessible from PHP side.

#### History of creation

Creation of simple Wordpress blog to allow adding information about pickets, strikes and other direct actions by a regional/brand section of workers union
is an easier way to create an elegant card, a personalized portfolio.

The problem is that Wordpress is very often attacked by various bots, they are brute forcing different parts 
like the administration panel, the login page, xmlrpc just to gain the access and infect and send their shitty spam.

This project was created to ban unwanted traffic, so the server could be more responsive and more secure.

Created originally by [Wolnościowiec team](https://github.com/Wolnosciowiec) for [Związek Syndykalistów Polski](http://zsp.net.pl) (Polish section of [International Workers Association](http://iwa-ait.org/) ).

## Installation

```
# via git
git clone https://github.com/zwiazeksyndykalistowpolski/php-denyhosts.git
composer install

# via composer
composer require create-project zwiazeksyndykalistowpolski/phpdenyhosts phpdenyhosts
```

## Configuration

In `configuration` directory there is a possibility to place multiple configuration files
for every domain/project, please use the `config.default.php.example` as an example.

See more:
- [More documentation about the configuration](./configuration/README.md)
- [Technical information about variables meaning, and a template of configuration](./configuration/config.default.php.example)

## Good practices

To secure installation of PhpDenyhosts you may want to generate a strong token
in every of your environment. Proposed length is 64 characters.

Other thing - you can place this application in a directory with random prefix or suffix.
Example: `denyhosts_9zbnKILG7e9HnVhW`. 
So the bots would have it more difficult to find out that you are using this project.

## Testing from shell

To simulate logs parsing you can add an environment variable "PDH_SIMULATE" that would
tell to not save anything, just print the logs.

Example:
```
PDH_SIMULATE=true env=default php index.php
```

## TODO

- unit tests