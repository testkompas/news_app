# News app docker and environtment config

This repository contains Dockerfile and environment config for front-end and back-end application, 
and docker-compose file to run whole application.

Deployed application will consist of Back-end application and front-end application for our News App, 
Mysql Database use to store News App data, and Adminer to view table in our Mysql Database.

To run docker-compose, the Front-end and Back-end News App application folder must be placed inside root directory of this repository.
The End result of this project structure will be as following.

    root_dir/
    |--news_app_fe/
    |--news_app_be/
    |--app_be.env
    |--app_fe.env
    |--docker-compose.yaml
    |--Dockerfile_be
    |--Dockerfile-fe
    |--mysql.env

All deployed container will use same bridge network "web" , Back-end News App container depends on Mysql Database container,
and Front-end News App container depends on Back-end News App container.

To deploy the application you will need docker and docker-compose installed in your machine.
After installation completes, run `docker-compose up --build -d` command, this command will c5reate bridge network "web",
and create new volume "dbdata" and bind the volume to out Mysql database container.

Back-end News app can be accessed from port :8100
Front-end News app can be accessed from port :3000
Mysql Database can be accessed from port :3307
Adminer can be accessed from port :8080
