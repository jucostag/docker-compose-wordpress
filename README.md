# DOCKER COMPOSE FOR WORDPRESS

This is a docker-compose file for WordPress applications. You can easely build a local docker environment with a customized URL and PHP settings. Feel free to use as a base and customize as you need.

#### Requirements:

- Docker
- A WordPress project

#### About the enviromnent:

- PHP 7.4.5 with FPM and the riquired libs for WP:
    - libpng
    - intl
    - xmlrpc
    - soap
    - zip
    - mysqli
- Nginx latest version available on docker hub
- MySQL latest version available on docker hub
- Dedicated volumes for wp-content uploads and MySQL data.
- PHPMyAdmin

#### How to use it:

- Clone or download the repository files into the root of your WordPress project.

- Include the database information on wp-config.php.
````
// ** Configurações do MySQL - Você pode pegar estas informações com o serviço de hospedagem ** //
/** O nome do banco de dados do WordPress */
define( 'DB_NAME', 'wp_db' );

/** Usuário do banco de dados MySQL */
define( 'DB_USER', 'root' );

/** Senha do banco de dados MySQL */
define( 'DB_PASSWORD', '123.456' );

/** Nome do host do MySQL */
define( 'DB_HOST', 'mysql' );

/** Charset do banco de dados a ser usado na criação das tabelas. */
define( 'DB_CHARSET', 'utf8' );

/** O tipo de Collate do banco de dados. Não altere isso se tiver dúvidas. */
define( 'DB_COLLATE', '' );
````

- Run docker-compose on command line
````
docker-compose up -d
````

- You can now access you're project **http://mywordpress.com.br** and phpmyadmin **http://localhost:8001**.

#### Some tips below:

- The database name and root password for MySQL service are in **docker/env/mysql.env**. This service uses root user.
- If you want to customize you're local URL, go to **docker/nginx/nginx.conf** and change the server_name on line 33.
- If you need to customize PHP configuration for your project, like memory_limit or max_execution_time for example, use the **docker/php/uploads.ini** file.

on http://localhost:8001