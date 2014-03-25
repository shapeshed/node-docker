# node-docker

This is a base image for Node.js applications in docker.

You can use it to run Node.js applications directly or as a base to build other images.

## How to start your application

The image assumes that you have defined in `package.json` how `npm start` will start your application

    {
      "name": "some-app",
      "version": "0.0.1",
      "author": "George Ornbo <george@shapeshed.com>",
      "description": "some description",
      "scripts": {
        "start": "node app.js"
      }
    }

## Adding a volume

The image assumes that your site is located at `/srv`. So you will need to specify a volume when creating a container. 

    sudo docker run -v /some/local/path:/srv -p 8080:8080 -i shapeshed/nodejs

## Setting the application port

No ports are exposed in the image so you will need to set these when creating the container to align with your application port. In this example the node app listens on 8080.

    sudo docker run -v /some/local/path:/srv -p 8080:8080 -i shapeshed/nodejs
