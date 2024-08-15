FROM alpine:3.14

LABEL maintainer="defrindr@gmail.com"

# Install dependencies
RUN apk add --no-cache nodejs npm

# Installing dependencies
WORKDIR /modules
COPY ./src/package.json /modules
RUN echo "Installing package"

# install node packages
RUN npm set progress=false && npm config set depth 0
RUN npm install

# Menggunakan nodemon untuk utility
RUN npm install -g nodemon

ENV NODE_PATH=/modules/node_modules

# Setup working directory
WORKDIR /app
COPY ./src /app

VOLUME ["/app"]

CMD ["nodemon", "start"]

# Expose the port (optional, if your app runs on a specific port)
EXPOSE 3000