docker-compose up <- run after updating the docker-compose.yml file. Builds the docker container using docker-compose.yml file.
docker-compose down <- stops and deletes the docker container.

# Clear the Database:
docker volume ls <- list all the files on docker. looking for something similar to [project name]_dev-db-data>
docker-compose down <- shuts down the container. Cannot delete the volume on a running container>
docker volume rm recipe-app-api_dev-db-data <- removes the database data>
docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate" <- rebuilds the container and adds the Django migrations>

# Add a python package:
add package to requirements.txt
docker-compose build

# Make a model (work flow):
1. write a test.
2. Create the model, inherit form Models.model
3. register the model with the [app] > admin.py > admin.site.register(models.Recipe) <makes the model available for admin site>
4. run manage.py makemigrations. Note: no need to migrate when testings (the test runner will make all migrations)

# Music:
Howling by Gunnar Olsen
New Year by bad snacks
Benji by Dyalla
Lifelong by Anno Domini Beats
Wandering by Gunnar Olsen