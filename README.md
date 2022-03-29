## 1. Docker running Postgres (public)

Follow along YouTube [tutorial](https://www.youtube.com/watch?v=aHbE3pTyG-Q) | [Postgres image](https://hub.docker.com/_/postgres) used 

- pull Postgres Alpine as this is the lightest version, excellent for testing and getting started wit

- exposed the container port to public by adding `-p 5432:5432`  
 

```
$ docker pull postgres:alpine 
$ docker run --name some-postgres -e POSTGRES_PASSWORD=somesecretpassword -d -p 5432:5432 postgres:alpine
$ docker images # to display images
$ docker ps
$ docker run
$ docker exec -it some-postgres bash
$ pwd
$ ls # to see the file structure
$ psql -U postgres # to enter the Postgres mode with the root Postgres user
$ \du # to show what kind of user we're using
$ create database test;
$ \l

```

### Connect to the container from the local machine

Make sure some version of psql is installed locally (e.g. [via homebrew](https://formulae.brew.sh/formula/postgresql))

(check: `less ~/.zshrc`)

```
$ psql -h localhost -p 5432 -U postgres
$ create database test2;
$ \c test2 # connect to it
$ create table student();
$ \dt;
$ \d student;
```

## 2. Docker running a Node.js app

Following Docker [docs](https://docs.docker.com/get-started/02_our_app/)
