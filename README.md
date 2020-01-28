If you are having IP issues, WP saves the domain/host to the db so docker-compose down -v 
may be the way to fix it.

If you can't save db - sudo chown -r $USER:$USER .

to load from existing source create folders wp-data and wp-app,
and copy db dumb to wp-data and existing wordpress build to wp-app
and use 'docker-compose up'



This will create the containers and populate the database with the 
given dump. You may set your host entry and change it in the database, 
or you simply overwrite it in wp-config.php by adding:

define('WP_HOME','http://wp-app.local');
define('WP_SITEURL','http://wp-app.local');

