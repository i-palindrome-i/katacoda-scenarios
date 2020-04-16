For our last steps, we're going to move the application, adjust permissions, and configure Apache to serve it. 

Lets move our project to a more standard web server location:
`sudo mv demo /var/www/html/`{{execute}}

Adjust the group for the application so the webserver has the proper access to the files:
`sudo chgrp -R www-data /var/www/html/demo/`{{execute}}

Set permissions for the storage folder: 
`sudo chmod -R 775 /var/www/html/demo/storage`{{execute}}

Now we need to tell Apache about our site. Let's move to the available sites directory:
`cd /etc/apache2/sites-available`{{execute}}

Create and edit a file for our site:
`sudo nano laravel.conf`{{execute}}

Within that file, copy and paste the following configuration (due to some copy/paste artifact, you'll have to move the `</VirtualHost>` to its own line manually after you paste this):
<pre class="file" data-target="clipboard">
&lt;VirtualHost *:80&gt;
  DocumentRoot /var/www/html/demo/public
  &lt;Directory /var/www/html/demo/public&gt;
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order allow,deny
    allow from all
    Require all granted
  &lt;/Directory&gt;
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/access.log combined
&lt;/VirtualHost&gt;
</pre>

We then need to disable the default virtual host using `sudo a2dissite 000-default.conf`{{execute}} and then enable ours with `sudo a2ensite laravel`{{execute}}.

After restarting Apache:
`sudo systemctl restart apache2`{{execute}}

Click the plus sign (+) next to where the UI says "Terminal" and choose "View HTTP port 80 on Host 1".

If everything went well, you should be greeted by the default Laravel application home page.
