[Composer](https://getcomposer.org/) is a dependency manager for PHP and is used by Laravel to manage.... dependencies.

Composer provides an installer file at https://getcomposer.org/installer, which is actually PHP code itself. 

Change to our `$HOME` directory with `cd ~`{{execute}} as somewhere to save this file temporarily.

We can get this file with curl and pipe it to PHP for execution, which will install it:
`curl -sS https://getcomposer.org/installer | php`{{execute}}
(`-sS` is [s]ilent mode, but still [S]hows errors)

On success, that creates a `composer.phar` file in the current directory. We can technically use it from here, but that isn't always convenient.

We'll move it to the `/usr/local/bin` directory so other users can access it:
`sudo mv composer.phar /usr/local/bin/composer`{{execute}}

A benefit of moving and renaming `composer.phar` is that we can now call composer by typing `composer`{{execute}}.

This gives us a retro "Composer" graphic and a list of its available commands.