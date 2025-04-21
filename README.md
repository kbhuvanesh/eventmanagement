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
6. Run SQL commands for all database files which is present in database/migrations folder
php artisan migrate --path=database/migrations/2023_08_16_183439_create_registrations_table.php
7. run below commands from inside project folder
php artisan cache:clear && php artisan route:cache
8. Register as User from home page
9. once user register, login using username and password
10. Create a category 
11. Create an event
12. attendees can register from homepage by clicking each event
13. List of registered events can be viewed on Attendees page



Pending items to finish

1. Validation for duplicate event
2. Unit and integration testing
3. API documentation using postman or swagger