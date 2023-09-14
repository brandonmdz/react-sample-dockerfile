# Dockerizing a Simple React App

This project dockerize a sample react project using the typescript template.

## How this work

### `FROM node:16.10.0-alpine`

We start with a node image based on alpine OS.

### `WORKDIR /app`

Set the current directory from this point to be /app.

### `COPY package.json ./`

Copy the package.json file inside the container image.

### `RUN yarn install`

Install dependencies using **yarn install.**

### `COPY . .`

Copy source code.

### `EXPOSE 3000`

Inform docker which port the server will be exposed to.

### `RUN yarn build`

Production build which in react can be done by running yarn build and placing the output in a static web server such as an nginx if you want.

### `CMD ["yarn", "start"]`

Define which command gets executed on startup.

## Do it yourself

You can do this from scratch in your local environment, be sure to have Node and Docker installed on your machine with the following commands:

`$ node -v`
`$ yarn -v`
`$ docker -v`

Now you need to run the following command:

$ npx create-react-app react-sample --template typescript

And you can start the app served in the port **:3000** with:

`$ cd react-sample
$ yarn start`

### `.dockerignore`

Be sure to add a .dockerignore file to avoid adding our local dependencies inside the container image like the one I upload ignoring the following folder:

`node_modules/`
