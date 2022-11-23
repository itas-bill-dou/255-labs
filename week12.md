# Lab - WordPress

## Objective

Know how to install a WordPress website with https in Docker and can install theme, plugin and pages.

## Scenario

You are a web designer and help one client set up a WordPress website and also demonstrate how to install a theme, plugin and page creation.

## Tasks

We will use Docker to create the website. However, you can select Xampp instead to finish it.

**Docker:** Note that you need to stop all Laravel container to let port 80 free.
**Xampp:** You need to create a vhost for the website

For either case, you need to edit hosts file to ensure my-wordpress.local pointing to 127.0.0.1

- Running website at http://my-wordpress.local in Docker or Xampp (vhost)
- Install a custom theme (real estate, restaurant, community park, school, etc)
- Install 3 plugins. A useful one is when you maintain your website, showing a "under construction" page.
- Create a menu as navigation bar
- Create 3 pages such as HomePage, about and service.
- Access WordPress database through any database client tool.
- Backup database sqldump (explain to me how you do it)
- Self-learning: install local SSL cert through mkcert tool

docker-compose.yml

```yml
version: "3.3"

services:
  db:
    image: mysql:5.7
    volumes:
      - ./db_data:/var/lib/mysql
    ports:
      - "3306:3306"
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: somewordpress
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    working_dir: /var/www/html
    # this will map the wordpress files into the current directory
    volumes:
      - .:/var/www/html
    ports:
      - "5050:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
```

Show me when you complete the lab.

Last udpate: Nov 23,2022
