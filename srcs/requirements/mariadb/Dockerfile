FROM debian:buster

RUN apt-get update && apt-get install -y mariadb-server

# Copy custom MariaDB configuration file (optional)
COPY my.cnf /etc/mysql/my.cnf

# Expose port 3306 for MariaDB
EXPOSE 3306

# Start MariaDB
CMD ["mysqld"]