# Waltmart challenge - Project Deployment

## Description

This repository exist with the propose of make the life easier while deploying
the [Backend](https://github.com/Esequiel378/waltmart-challenge-backend) and the
[Frontend](https://github.com/Esequiel378/waltmart-challenge-frontend) of this
challenge in the same server

## Setup

First you need to get the source code for all the repositories

```shell
git clone https://github.com/Esequiel378/waltmart-challenge-backend.git

git clone https://github.com/Esequiel378/waltmart-challenge-frontend.git

git clone https://github.com/Esequiel378/waltmart-challenge-deployment.git
```

### The .env files

Each of this projects needs it own .env file, you can refere to they README

+ [Backend README](https://github.com/Esequiel378/waltmart-challenge-backend/blob/master/README.md)

+ [Forntend README](https://github.com/Esequiel378/waltmart-challenge-frontend/blob/master/README.md)

This project need a .env file in the root directory, with the next variables

```Python
DATABASE_HOST=database
DATABASE_USERNAME=root
DATABASE_PASSWORD=secret
```

They may looks familiar to you, even you may think that you see them before,
and yes, you do, in order to build the database container, the project need some
variables from de [Backend](https://github.com/Esequiel378/waltmart-challenge-backend)
project.

The best way to achieve this, is simple creating a symlinc
with the [Backend](https://github.com/Esequiel378/waltmart-challenge-backend)
.env file, in order to avoid conflicts in the future

```shell
ln ../waltmart-challenge-backend/.env .env
```

Since the project use docker-compose, you can deploy by running

```shell
docker-compose -f production.yml build
```

```shell
docker-compose -f production.yml up
```

Now you can visit your server ip and you will see the Frontend app running

Locally you cant go to http://localhost