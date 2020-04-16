In this lesson, we're going to be using Laravel 7, which requires PHP >= 7.2.5 and a number of PHP extensions.

To meet this requirement, we'll install PHP 7.3. Unfortunately, this is not currently available in Ubuntu's default repositories. It is available in a Personal Package Archives (PPA) published by [Ondrej Sury](https://launchpad.net/~ondrej).

Add this repository now using:
`sudo add-apt-repository ppa:ondrej/php`{{execute}}

(Throughout this lesson, keep an eye on the terminal messages, you may need to confirm some of these commands)

Now use `sudo apt update`{{execute}} to download the package information from this new source.

Install PHP and the extensions required by Laravel using:
`sudo apt install php7.3 php7.3-cli php7.3-common php7.3-zip php7.3-mbstring php7.3-xml`{{execute}}

Once that command completes, we can check that installation succeeded with `php -v`{{execute}}. It should report back that we are using some version of PHP 7.3.x.

Now that PHP is installed with the correct version, we're ready to install a dependency manager.