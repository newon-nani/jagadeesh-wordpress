# jagadeesh-wordpress
# WordPress Setup with Nginx Using Docker Compose

This guide will walk you through setting up a WordPress website with Nginx using Docker Compose. We'll start by configuring the web server, defining environment variables, registering a domain, obtaining SSL certificates, optimizing performance, and finally launching the site locally.

## Prerequisites

1. AWS free tier account
2. Custom domain from noip.com and provide the vps server IP in the records
3. VPS machine with ubuntu 22.04
4. Pre installed packages like docker, docker-compose & certbot.
5. Security group with strict inbound rules for incoming traffic

## Step 1: Clone the repository

1. Clone the repository
   ```sh
   cd wordpress
   ```

## Step 2: Defining Environment Variables
1. Create a .env file in your project directory:
   ```sh
   nano .env
   ```
2. Define the following environment variables in the .env file:
   ```sh
   MYSQL_ROOT_PASSWORD=your_root_password
   MYSQL_USER=your_wordpress_database_user
   MYSQL_PASSWORD=your_wordpress_database_password
   ```
Be sure to replace your_root_password, your_wordpress_database_user, and your_wordpress_database_password with your desired values.

## Step 3: Necessary changes for web server config
Add domain related config changes to the nginx config.

## Step 4: Obtaining SSL Certificates and Credentials
Obtain SSL certificates for your domain using Certbot:
   ```sh
   sudo certbot --nginx -d jagadeesh-wordpress.ddns.net -d www.jagadeesh-wordpress.ddns.net
   ```
Follow the prompts to configure SSL for your domain.

## Step 5: Providing SSL certificates for web server
provide the genearted ssl certificates location paths in the nginx config file
## Step 6: Performance Optimization
Perform optimizations for Nginx performance, caching, and compression. Provide relevant details or links to optimization guides if applicable.

For gzip/compression use this blocks:
![image](https://github.com/newon-nani/jagadeesh-wordpress/assets/90192758/4f602c5c-d35c-4c57-b1af-73236fd6de75)


For caching use this blocks:
![image](https://github.com/newon-nani/jagadeesh-wordpress/assets/90192758/e2478c90-649c-4931-8dba-89cf8ca1d3f7)



## Step 7: Launch the Site using docker compose commands
Start your Docker Compose services:
   ```sh
   docker-compose up -d
   ```
Access the site using your registered domain and perform any additional settings or configurations required.

Now, you have successfully set up WordPress with Nginx using Docker Compose, obtained SSL certificates, and optimized your site for performance. You can access your WordPress site at your registered domain.
