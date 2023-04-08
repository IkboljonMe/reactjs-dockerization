# React JS Project Dockerization for Development and Production

This README file provides instructions for running a React JS project, created using `create-react-app`, in a Docker container for development and production modes. The project contains separate `.env` files for both development and production modes. In development mode, the project runs on [localhost:3000](http://localhost:3000), while in production mode, it runs on [localhost:8080.](http://localhost:8080)

## Requirements

Make sure you have installed:

- Docker Engine

Check for Docker Engine:

```
docker --version
```

If it is not installed, [visit to this page](https://docs.docker.com/engine/)

## Usage

There are two ways to run the project in a Docker container: using `docker-compose` command and using `docker run` command.

`docker-compose` is preffered.

### Using `docker-compose` Command

To run the project using docker-compose, use the following command:

```
docker-compose -f docker-compose-dev.yml up -d
```

You can see result on [localhost:3000](http://localhost:3000)

For production mode, use the following command:

```
docker-compose -f docker-compose-prod.yml up -d
```

You can see result on [localhost:8080](http://localhost:8080)

To stop and remove the containers, use the following command:

```
docker-compose -f <docker-compose-file> down
```

## Using `docker run` Command

You can run the project in a Docker container for development mode using the following command:

```
docker run -it --rm -v ${PWD}:/app -v /app/node_modules -p 3000:3000 --env-file .env.dev react-docker:dev
```

For production mode, use the following command:

```
docker run -it --rm -p 8080:80 --env-file .env react-docker:prod
```

## Conclusion

This README file demonstrates a simple way to dockerize a React JS project for development and production modes. To run the project in a Docker container, you can use either the `docker run` or `docker-compose` command based on your requirements.

For more information on how to use Docker CLI in the terminal, please refer to other resources and README files.

Thank you for using this README file. Good luck with your project!
