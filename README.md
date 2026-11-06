# php-docker-dev

A Docker YAML file for PHP 8 quick development with Apache and DB. It fetches the latest version of PHP.

Composer is inlcuded as well.

# Configuration

Before starting the container dont forget to change the username and password of the db user

# Just ...

- Inside the folder run: docker compose up [to start the stack]
- open your browser to http://localhost:8080 [for the latest PHP8]
- open your browser to http://localhost:8081 [to admin the DB]
- hit: Ctrl+c [to stop the stack]

# Network

If you want to connect the docker in a different network eg. proxy :

- docker network connect proxy <container_id>

# Updating

- docker compose down
- docker compose pull
- docker compose up --build

# Your code ...

Add your code inside the src folder and you can view it instantly inside docker!

Do not forget to (to allow the web server to handle the files properly): chmown -R www-data: ./src
