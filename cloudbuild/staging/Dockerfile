FROM gcr.io/distroless/base

# RUN echo -e "http://nl.alpinelinux.org/alpine/latest-stable/main\nhttp://nl.alpinelinux.org/alpine/latest-stable/community" > /etc/apk/repositories

# The latest alpine images don't have some tools like (`git` and `bash`).
# Adding git, bash and openssh to the image
# RUN apk update && apk upgrade && apk add --no-cache bash git openssh make autoconf gcc libc-dev sudo procps curl

COPY ./bin/gulab /var/www/gulab/bin/gulab
COPY ./env.json /var/www/gulab/env.json
COPY ./views /var/www/gulab/views
COPY ./commands /var/www/gulab/commands

COPY ./handlers /var/www/gulab/handlers
COPY ./middlewares /var/www/gulab/middlewares

COPY ./packages /var/www/gulab/packages
COPY ./repositories /var/www/gulab/repositories
# COPY ./routers /var/www/gulab/routers
COPY ./validations /var/www/gulab/validations
COPY ./services /var/www/gulab/services

COPY ./models /var/www/gulab/models

# Set the Current Working Directory inside the container
WORKDIR /var/www/gulab

# Expose port 8888 to the outside world, 40000 for debugging
EXPOSE 8002

ENTRYPOINT ["./bin/gulab", "start"]