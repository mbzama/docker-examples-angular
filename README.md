# Running app without Docker

## Install Deps
Run `npm install`


## Development server
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.


## Code scaffolding
Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.


## Build
Run `ng build --prod` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.


## Deploying to Web server (Nginx)
Copy files from `dist/` directory to `/var/www/html`. Navigate to `http://localhost`



# Running app with Docker

## Build docker image
Instructions for building docker image are specified in `Dockerfile`. Run `docker build -t docker-examples-angular .`


## Create/Run docker container
Run `docker run -d -p 8888:80 --name angular-app-container docker-examples-angular`

If you encounter this error-> docker: Error response from daemon: Conflict. The container name "/angular-app-container" is already in use by container "d46221f9f147f1881d3a19c728d70d60a9f70f4e3b54b96c7d865604d377e311". You have to remove (or rename) that container to be able to reuse that name.

Remove the container using `docker rm -f angular-app-container`

## Accessing the app
Navigate to `http://localhost:8888/`


## To login to running container
Run `docker exec -it angular-app-container sh` and inspect the files using regular linux commands such ls, cat .,


## Stop the docker containers
Run `docker stop angular-app-container`


## To run the app using docker-compose
Run `docker-compose up -d`


## To scale the containers or run multiple copies of the app
Run `docker-compose scale web=3`. To verify run `docker ps` to view the active containers
![alt text](https://github.com/mbzama/docker-examples-angular/blob/master/scale.png)


## Accessing the app
Navigate to `http://localhost:8001/`


## Stop the docker containers
Run `docker-compose stop`


## Stop & remove the docker containers
Run `docker-compose down`




