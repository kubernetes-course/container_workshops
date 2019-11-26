FROM node:latest

# BUILDING IMAGE
# SET ENV VARS
ENV APP_ROOT=/app
ENV APP_PORT=3000

# CREATE THE DIR AND CD INTO IT
WORKDIR ${APP_PORT}

# COPY FILES INTO THE IMAGE INTO /app
ADD main.js .
ADD package.json .
ADD public public
ADD views views

# RUN CMDS
RUN npm install


#PROVISIONING/RUNNING IMAGE
#CONTAINER EXPOSED PORT
EXPOSE ${APP_PORT}

#HEALTHCHECK FOR APP
HEALTHCHECK --interval=30s --timeout=5s --retries=3 CMD curl -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

ENTRYPOINT ["node", "main.js"]

