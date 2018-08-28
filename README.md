# tvcast-service
This project will provide the cast of all TV shows.

## Desription
This project consists of Node.js services which connects to the MongoDB instance. There is a Docker configuration which gives an ability to run all services in `DEV` as well as in `PROD` mode inside Docker containers. This is recommended, because of MongoDB instance which is provided as a separate Docker container.

## Running with Docker (recommended)
**Note: During development it was used Docker in version 18.06.0-ce-win72 (19098) for Windows.**

All of this commands should be run from the project root path `/`.

### Running in `DEV` mode
During running in `DEV` mode all services are running inside Docker containers. After any changes in the source code services will restart automagically.
```
yarn run compose:up:dev
```

In order to provide linting of the source code in watch mode just go to the appropriate service folder `/services/<foo-svc>/` and run in terminal:
```
yarn run lint:watch
```

### Running in `PROD` mode
In `PROD` mode containers are running in detached mode.
```
yarn run compose:up:prod
```

## Running without Docker
There is a possiblity to run all services without Docker, but then we need to provide connection string and credentials to the external MongoDB instance and start all Node.js services manually. For this purpose all commands should be run from inside of given service folder `/services/<foo-svc>/`.

### Running in `DEV` mode
This command starts TS linter and nodemon simultaneously which provides everything what is needed for development process.
```
yarn run start:dev
```

### Running in `PROD` mode
Running each Node.js service in `PROD` mode should be as follows:
```
yarn run build
yarn run start
```
