[Composer](https://getcomposer.org/) is a dependency manager for PHP and is used by Laravel to manage.... dependencies.

Composer provides an installer file at https://getcomposer.org/installer, which is actually PHP code itself. We can get this file with curl and pipe it to PHP for execution, which will install it:
`curl -sS https://getcomposer.org/installer | php`{{execute}}
(`-sS` is [s]ilent mode, but still [S]hows errors)

On success, that creates a `composer.phar` file in the current directory. We can technically use it from here, but that isn't always convenient.

We'll move it to our `bin` directory since that is likely a better place than the directory we happened to be in when we downloaded the file:
`sudo mv composer.phar /usr/local/bin/composer`{{execute}}

A benefit of moving and renaming `composer.phar` is that we can now call composer by typing `composer`{{execute}}.