
FROM node:latest as node
LABEL maintainer="devops@verity.ch"
RUN apt-get update -qq && apt-get install -qy \ 
    ca-certificates \
    bzip2 \
    curl \
    libfontconfig \
    --no-install-recommends
RUN mkdir -p /app
WORKDIR /app
COPY package*.json /app/
RUN npm install \
    && npm cache clean --force

COPY . .
EXPOSE 3000
CMD [ "node", "./bin/www" ]
