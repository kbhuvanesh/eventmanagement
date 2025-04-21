Run the following commands
1. git clone https://github.com/kbhuvanesh/eventmanagement.git em
2. "composer update" in project folder
3. create virtual hosting in apache file (httpd.conf) 
<VirtualHost _default_:8080>
  ServerName localhost
  ServerAlias localhost
  DocumentRoot "${INSTALL_DIR}/www/em/public/"
  <Directory "${INSTALL_DIR}/www/em/public">
    Options +Indexes +Includes +FollowSymLinks +MultiViews
    AllowOverride All
    Require local
  </Directory>
</VirtualHost>
5. change listener port in httpd.conf file to 8080
5. restart apache server
6. Rename env.project to .env file
7. Run SQL commands for all database files which is present in database/migrations folder
php artisan migrate --path=database/migrations/2023_08_16_183439_create_registrations_table.php
8. run below commands from inside project folder
php artisan cache:clear && php artisan route:cache
9. Open in browser this URL: http://localhost:8080/
10. Register as User from home page
11. once user register, login using username and password
12. Create a category 
13. Create an event
14. attendees can register from homepage by clicking each event
15. List of registered events can be viewed on Attendees page
16. Post man collections are named "Event Managment Systems.postman_collection.json"


Pending items to finish

1. Validation for duplicate event
2. Unit and integration testing