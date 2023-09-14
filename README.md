# Dockerizing a Simple React App

This project dockerize a sample react project. You can see the original source here: [Create React App](https://github.com/facebook/create-react-app).

## How this work

### `FROM`

We start with a node image based on alpine OS.

### `WORKDIR`

Set the current directory from this point to be /app.

### `COPY`

Copy the package.json & yarn.lock file inside the container image.

### `RUN`

Install dependencies using **yarn install.**

### `COPY`

Copy source code.

### `EXPOSE`

Inform docker which port the server will be exposed to.

### `RUN`

Production build which in react can be done by running yarn build and placing the output in a static web server such as an nginx if you want.

### `CMD`

Define which command gets executed on startup.

