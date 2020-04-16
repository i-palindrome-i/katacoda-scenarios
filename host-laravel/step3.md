At this point, we could clone an existing Laravel repo, but we're going to make a fresh Laravel app using the installer.

We use Composer to grab it with:
`composer global require laravel/installer`{{execute}}

Once installed, we need to add Composer's system wide `/vendor/bin` directory to the `PATH` so that we can access it:
`export PATH="$HOME/.config/composer/vendor/bin:$PATH"`{{execute}}

Now, we should have the Laravel installer cli. We can check with `laravel -v`{{execute}}