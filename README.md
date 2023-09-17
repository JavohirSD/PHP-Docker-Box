
# PHP-Docker-Box
Universal docker composition for PHP projects.</br></br>
Project includes: </br>
- Latest stable version of PHP with minimal extensions.
- Latest version of NGINX with standard configurations.
- PostgresSQL with default configurations
- Adminer - simple and lightweight database manager.
- Latest stable version of Redis with default configurations.


# Installation
1. Clone git repository into your project root. </br>
``` git clone https://github.com/JavohirSD/PHP-Docker-Box.git ```
   </br></br>
2. Change working directory.</br>
``` cd docker ```
   </br></br>
3. Edit ENV variables (optional but recommended)</br>
   </br>
4. Run the Docker composition.</br>
``` docker-compose up -d ```
____
Your project will run on http://localhost </br>
Database host will be ```pgsql``` for all services
___
 **Adminer configuration:**

 - **System:** PostgreSQL 
 - **Server:** pgsql