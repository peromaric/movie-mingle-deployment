# movie-mingle-deployment
Springboot and Angular practice

## Where's what?
Postgres is run from the docker container.
The app is served on http://localhost:4200.
Backend's swagger is on http://localhost:8080/swagger-ui.html.

It's not a production ready application (yet), just a showcase.

You basically open the webapp and browse around 5k movie entries.
When you click on an entry, you get a short/long description.
You can click on the TOP image and you get top 10 of all time ('till 2017) movies by revenue.
You can enter a year to get the top movies from that time by revenue (if 10 of them exist for that year).

## Project setup
There's two submodules containing backend and frontend respectively.
A docker compose file dockerizing the entire thing.
A dockerized postgres database used by the backend.
After cloning run the command to initialize and update the submodules:
```
git submodule update --init
```
I highly recommend running the app via. docker. Tested on two different laptops running Windows and Ubuntu.

## Run using docker
Make sure the following ports are free: 4200, 8080 and 5432!
It's all run on the host network, so it's shared with anything you've running on localhost.
Clone this repo and run it via:
```
docker compose -f docker-compose.yml up -d
```
You should se build output and that's it.

## Run using two windows of your favorite IDE
You still need docker to run the postgres database.
After you get it up and running, just run the following:
```
docker-compose -f docker-compose.yml up -d postgres
```
After this you can just manually run the two projects.