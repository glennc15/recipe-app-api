docker-compose up <- run after updating the docker-compose.yml file. Builds the docker container using docker-compose.yml file.
docker-compose down <- stops and deletes the docker container.

# Clear the Database:
docker volume ls <- list all the files on docker. looking for something similar to [project name]_dev-db-data>
docker-compose down <- shuts down the container. Cannot delete the volume on a running container>
docker volume rm recipe-app-api_dev-db-data <- removes the database data>
docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate" <- rebuilds the container and adds the Django migrations>