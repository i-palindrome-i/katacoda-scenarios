At this point, we could clone an existing Laravel repo, but we're going to make a fresh Laravel app using the installer.

We use Composer to add the Laravel installer globally with:
`composer global require laravel/installer`{{execute}}

Once installed, we need to add Composer's system wide `/vendor/bin` directory to the `PATH` so that we can access it:
`export PATH="$HOME/.config/composer/vendor/bin:$PATH"`{{execute}}

Now, we should have the Laravel installer cli. We can check with `laravel -V`{{execute}}

With the Laravel installer, we can now create a new `demo` app:
`laravel new demo`{{execute}}

This creates a new directory with the app, installs dependencies with Composer, generates an app key, and some other housekeeping.

When complete, we can use `ls`{{execute}} to ensure that there is indeed a `demo` directory in our home directory.