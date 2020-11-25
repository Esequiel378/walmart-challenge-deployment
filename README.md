# Walmart challenge - Project Deployment

## Description

This repository have the purpose of make the life easier while deploying
the [Backend](https://github.com/Esequiel378/walmart-challenge-backend) and the
[Frontend](https://github.com/Esequiel378/walmart-challenge-frontend) of this
challenge in the same server

Live demo [lider.co](http://165.22.3.102)

## Setup

First you need to get the source code for all the repositories

```shell
# Api - backend
git clone https://github.com/Esequiel378/walmart-challenge-backend.git

# Web App - frontend
git clone https://github.com/Esequiel378/walmart-challenge-frontend.git

git clone https://github.com/Esequiel378/walmart-challenge-deployment.git
```

### The .env files

Each of these projects needs its own .env file, you can refere to they README

+ [Backend README](https://github.com/Esequiel378/walmart-challenge-backend/blob/master/README.md)

+ [Forntend README](https://github.com/Esequiel378/walmart-challenge-frontend/blob/master/README.md)

This project need a .env file in the root directory, with the next variables

```Python
DATABASE_HOST=database
DATABASE_USERNAME=root
DATABASE_PASSWORD=secret
```

They may looks familiar to you, even you may think that you see them before,
and yes, you do, in order to build the database container, the project need some
variables from de [Backend](https://github.com/Esequiel378/walmart-challenge-backend)
project.

The best way to achieve this, is just creating a symlinc
with the [Backend](https://github.com/Esequiel378/walmart-challenge-backend)
.env file, in order to avoid conflicts in the future

```shell
# within the root directory
ln ../walmart-challenge-backend/.env .env
```

Since the project use docker-compose, you can deploy by running

```shell
# build api and database images
docker-compose -f production.yml build

# create api and database containers
docker-compose -f production.yml up
```

Now you can visit your server ip/domain or http://localhost to view the [App](https://github.com/Esequiel378/walmart-challenge-frontend)
running

## Related Projects

+ Lider demo frontend https://github.com/Esequiel378/walmart-challenge-frontend

+ Lider demo backend https://github.com/Esequiel378/walmart-challenge-backend

## TODO

- [ ] Create a BFF

- [ ] SSL cerificates
