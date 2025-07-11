# Go to the docker hub docs for mysql to learn how to build your Dockerfile 
FROM mysql:8.0.33
LABEL "Prokect"="Vprofile"
LABEL "Author"="Mohannad"
# Based on the docker hub docs for mysql, we have to set root password and db name.
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"
# Copy the sql file to the location mentioned in the docs
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql