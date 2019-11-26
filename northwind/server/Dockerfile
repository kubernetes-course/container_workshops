FROM node:latest


ENV APP_ROOT=/app
ENV APP_PORT=3000
ENV DB_HOST=localhost
ENV DB_PORT=3306
ENV DB_USER=root
ENV DB_PASSWORD=changeit
ENV INSTANCE_IP_ADDRESS=172.17.0.2

WORKDIR ${APP_ROOT}}

ADD main.js .
ADD package.json .
ADD config config
ADD public public
ADD views views

RUN npm install

EXPOSE ${APP_PORT}

HEALTHCHECK --interval=60s --timeout=30s --retries=3 CMD curl -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

ENTRYPOINT ["node", "main.js"]