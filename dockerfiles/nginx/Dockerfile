FROM nginx:stable-alpine

ARG UID
ARG GID

ENV UID=${UID}
ENV GID=${GID}

# The dialout group in Alpine Linux and the MacOS staff group both have gids of 20. Let's just get rid of it because we aren't using it.
RUN delgroup dialout

# Laravel user assignment
RUN addgroup --gid ${GID} --system laravel
RUN adduser --ingroup laravel --disabled-password --shell /bin/sh --uid ${UID} --system laravel
RUN sed -i "s/user  nginx/user laravel/g" /etc/nginx/nginx.conf

# Nginx config
ADD ./conf/default.conf /etc/nginx/conf.d/

RUN mkdir -p /var/www/html