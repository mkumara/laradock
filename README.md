Search Engine local environment

This project is based on laradock PHP Docker environment

cp env-example .env
./up


Note:

There may be port conflicts.

Change the port forwardings in .env file



One example setup with different fort forwarding

```###########################################################
###################### General Setup ######################
###########################################################

### Paths #################################################

# Point to the path of your applications code on your host
APP_CODE_PATH_HOST=../

# Point to where the `APP_CODE_PATH_HOST` should be in the container. You may add flags to the path `:cached`, `:delegated`. When using Docker Sync add `:nocopy`
APP_CODE_PATH_CONTAINER=/var/www:cached

# Choose storage path on your machine. For all storage systems
DATA_PATH_HOST=/Users/jayantha/.laradock/data
MYSQL_WORKINGDATA_PATH=../data
### Drivers ################################################

# All volumes driver
VOLUMES_DRIVER=local

# All Networks driver
NETWORKS_DRIVER=bridge

### Docker compose files ##################################

# Select which docker-compose files to include. If using docker-sync append `:docker-compose.sync.yml` at the end
COMPOSE_FILE=docker-compose.yml

# Change the separator from : to ; on Windows
COMPOSE_PATH_SEPARATOR=:

# Define the prefix of container names. This is useful if you have multiple projects that use laradock to have seperate containers per project.
COMPOSE_PROJECT_NAME=laradock

### PHP Version ###########################################

# Select a PHP version of the Workspace and PHP-FPM containers (Does not apply to HHVM). Accepted values: 7.2 - 7.1 - 7.0 - 5.6
PHP_VERSION=7.2

### PHP Interpreter #######################################

# Select the PHP Interpreter. Accepted values: hhvm - php-fpm
PHP_INTERPRETER=php-fpm

### Docker Host IP ########################################

# Enter your Docker Host IP (will be appended to /etc/hosts). Default is `10.0.75.1`
DOCKER_HOST_IP=10.0.75.1

### Remote Interpreter ####################################

# Choose a Remote Interpreter entry matching name. Default is `laradock`
PHP_IDE_CONFIG=serverName=laradock

### Windows Path ##########################################

# A fix for Windows users, to ensure the application path works
COMPOSE_CONVERT_WINDOWS_PATHS=1

### Environment ###########################################

# If you need to change the sources (i.e. to China), set CHANGE_SOURCE to true
CHANGE_SOURCE=false

### Docker Sync ###########################################

# If you are using Docker Sync. For `osx` use 'native_osx', for `windows` use 'unison', for `linux` docker-sync is not required
DOCKER_SYNC_STRATEGY=native_osx

###########################################################
################ Containers Customization #################
###########################################################

### WORKSPACE #############################################

WORKSPACE_COMPOSER_GLOBAL_INSTALL=true
WORKSPACE_COMPOSER_REPO_PACKAGIST=
WORKSPACE_INSTALL_NODE=true
WORKSPACE_NODE_VERSION=node
WORKSPACE_NPM_REGISTRY=
WORKSPACE_INSTALL_YARN=true
WORKSPACE_YARN_VERSION=latest
WORKSPACE_INSTALL_NPM_GULP=true
WORKSPACE_INSTALL_NPM_BOWER=true
WORKSPACE_INSTALL_NPM_VUE_CLI=true
WORKSPACE_INSTALL_PHPREDIS=true
WORKSPACE_INSTALL_WORKSPACE_SSH=false
WORKSPACE_INSTALL_SUBVERSION=false
WORKSPACE_INSTALL_XDEBUG=false
WORKSPACE_INSTALL_PHPDBG=false
WORKSPACE_INSTALL_LDAP=false
WORKSPACE_INSTALL_SOAP=false
WORKSPACE_INSTALL_IMAP=false
WORKSPACE_INSTALL_MONGO=false
WORKSPACE_INSTALL_AMQP=false
WORKSPACE_INSTALL_MSSQL=false
WORKSPACE_INSTALL_DRUSH=false
WORKSPACE_DRUSH_VERSION=8.1.17
WORKSPACE_INSTALL_DRUPAL_CONSOLE=false
WORKSPACE_INSTALL_AEROSPIKE=false
WORKSPACE_INSTALL_V8JS=false
WORKSPACE_INSTALL_LARAVEL_ENVOY=false
WORKSPACE_INSTALL_LARAVEL_INSTALLER=false
WORKSPACE_INSTALL_DEPLOYER=false
WORKSPACE_INSTALL_PRESTISSIMO=false
WORKSPACE_INSTALL_LINUXBREW=false
WORKSPACE_INSTALL_MC=false
WORKSPACE_INSTALL_SYMFONY=false
WORKSPACE_INSTALL_PYTHON=false
WORKSPACE_INSTALL_IMAGE_OPTIMIZERS=false
WORKSPACE_INSTALL_IMAGEMAGICK=false
WORKSPACE_INSTALL_TERRAFORM=false
WORKSPACE_INSTALL_DUSK_DEPS=false
WORKSPACE_INSTALL_PG_CLIENT=false
WORKSPACE_INSTALL_SWOOLE=false
WORKSPACE_INSTALL_LIBPNG=false
WORKSPACE_PUID=1000
WORKSPACE_PGID=1000
WORKSPACE_CHROME_DRIVER_VERSION=2.32
WORKSPACE_TIMEZONE=UTC
WORKSPACE_SSH_PORT=2224
RACHET_PORT=8088
DONEE_RACHET_PORT=8089

### PHP_FPM ###############################################

PHP_FPM_INSTALL_ZIP_ARCHIVE=true
PHP_FPM_INSTALL_BCMATH=true
PHP_FPM_INSTALL_MYSQLI=true
PHP_FPM_INSTALL_TOKENIZER=true
PHP_FPM_INSTALL_INTL=true
PHP_FPM_INSTALL_IMAGEMAGICK=true
PHP_FPM_INSTALL_OPCACHE=true
PHP_FPM_INSTALL_IMAGE_OPTIMIZERS=true
PHP_FPM_INSTALL_PHPREDIS=true
PHP_FPM_INSTALL_MEMCACHED=false
PHP_FPM_INSTALL_XDEBUG=false
PHP_FPM_INSTALL_PHPDBG=false
PHP_FPM_INSTALL_IMAP=false
PHP_FPM_INSTALL_MONGO=false
PHP_FPM_INSTALL_AMQP=false
PHP_FPM_INSTALL_MSSQL=false
PHP_FPM_INSTALL_SOAP=false
PHP_FPM_INSTALL_GMP=false
PHP_FPM_INSTALL_EXIF=false
PHP_FPM_INSTALL_AEROSPIKE=false
PHP_FPM_INSTALL_PGSQL=false
PHP_FPM_INSTALL_GHOSTSCRIPT=false
PHP_FPM_INSTALL_LDAP=false
PHP_FPM_INSTALL_SWOOLE=false
PHP_FPM_INSTALL_PG_CLIENT=false
PHP_FPM_INSTALL_PCNTL=false

### PHP_WORKER ############################################

PHP_WORKER_INSTALL_PGSQL=false

### NGINX #################################################

NGINX_HOST_HTTP_PORT=18080
NGINX_HOST_HTTPS_PORT=1443
NGINX_HOST_LOG_PATH=./logs/nginx/
NGINX_SITES_PATH=./nginx/sites/
NGINX_PHP_UPSTREAM_CONTAINER=php-fpm
NGINX_PHP_UPSTREAM_PORT=9000

### MYSQL #################################################

MYSQL_VERSION=5.7
MYSQL_DATABASE=default
MYSQL_USER=default
MYSQL_PASSWORD=secret
MYSQL_PORT=3307
MYSQL_ROOT_PASSWORD=root
MYSQL_ENTRYPOINT_INITDB=./mysql/docker-entrypoint-initdb.d
MYSQL_WORKINGDATA_PATH=../data

### REDIS #################################################

REDIS_PORT=16379


### POSTGRES ##############################################

POSTGRES_DB=default
POSTGRES_USER=default
POSTGRES_PASSWORD=secret
POSTGRES_PORT=5432
POSTGRES_ENTRYPOINT_INITDB=./postgres/docker-entrypoint-initdb.d

### ELASTICSEARCH #########################################

ELASTICSEARCH_HOST_HTTP_PORT=9400
ELASTICSEARCH_HOST_TRANSPORT_PORT=9500


### LARAVEL ECHO SERVER ###################################

LARAVEL_ECHO_SERVER_PORT=6001
```