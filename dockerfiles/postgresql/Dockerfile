FROM postgres:15.1

ARG UID
ARG GID

ENV UID=${UID}
ENV GID=${GID}

RUN usermod -u ${GID} postgres && groupmod -g ${UID} postgres


