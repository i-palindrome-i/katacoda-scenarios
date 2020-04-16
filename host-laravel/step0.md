Before we get started, we can check what user we are logged into in this environment using `whoami`{{execute}}. Hmmmm, we are `root`. As any fan of [linuxquestions.org](linuxquestions.org) would know, we [probably](https://www.linuxquestions.org/questions/linux-newbie-8/disadvantages-of-using-root-194884/) [shouldn't](https://www.linuxquestions.org/questions/linux-newbie-8/what-is-so-dangerous-about-using-root-47298/) be doing things as the `root` user (and in fact, several of the steps will raise warnings if we soldier on).

Let's add a new user `laravel` (pick a fun password and use the default for the remaining user details):
`adduser laravel`{{execute}}

Now we need to add them to the `sudo` group:
`usermod -aG sudo laravel`{{execute}}

And finally, switch to the `laravel` user for the remainder of this lesson:
`su laravel`{{execute}}

(You can check this worked using `whoami`{{execute}})