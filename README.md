# php-docker-dev

A Docker YAML file for PHP 8 quick development with Apache and DB. It fetches the latest version of PHP.

Composer is included as well.

# Configuration

Before starting the container dont forget to change the username and password of the db user.

Also change the PORTs accordingly as needed.

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

# Installed PHP extensions

```bash
docker exec -it <container_id> php -m

[PHP Modules]
Core
ctype
curl
date
dom
fileinfo
filter
hash
iconv
json
ldap
lexbor
libxml
mbstring
mysqli
mysqlnd
openssl
pcre
PDO
pdo_mysql
pdo_sqlite
Phar
posix
random
readline
Reflection
session
SimpleXML
sodium
SPL
sqlite3
standard
tokenizer
uri
xml
xmlreader
xmlwriter
Zend OPcache
zip
zlib

[Zend Modules]
Zend OPcache
```
