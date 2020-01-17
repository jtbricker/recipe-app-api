# recipe-app-api
recipe app api source code

## Setup

### Building the docker image

Run `docker build .` in this directory to build the docker image from the `Dockerfile`.

### Running the app

The system is defined in the `docker-compose.yml`.  This file references the `Dockerfile` (services:app:build:context:.) and syncs the local `./app` folder with the container's copy of the folder.  To start the app, run `docker-compose up` in this directory.

### Running Commands in the docker container
Use the following command to run commands in your container environment:

```bash
docker-compose run app sh -c "[command]"
```

or more simply

```bash
docker-compose run app [command]
```

Here, `app` is the name of the app given in the `docker-compose.yml` file.  The `sh -c` syntax allows us to run multiple commands using `&&` between commands.

## Running Tests and Lint

You can run the following command to run tests and flake8 linter on the codebase:

```bash
docker-compose run app sh -c "python manage.py test && flake8"
```



