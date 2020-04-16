The first thing that we need to enable for Laravel to work with Apache is the `mod_rewrite` Apache module. This allows us to use clean URLs. Any files requested that aren't found in the filesystem get requested by the `index.php` controller.

The command to enable the module is:
`sudo a2enmod rewrite`{{execute}}

We then need to restart Apache:
`sudo systemctl restart apache2`{{execute}}

We can examine the dump of Apache modules to ensure that it is enabled:
`apachectl -t -D DUMP_MODULES | grep rewrite`{{execute}}
(If successful, we'll see `rewrite_module (shared)` listed)