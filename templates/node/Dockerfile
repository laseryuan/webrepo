FROM node:10

# Create app directory
WORKDIR /usr/src/app
RUN chown node:node /usr/src/app

# RUN npm install -g {global_packages}

USER node

COPY --chown=node app/package*.json ./
RUN npm install

COPY --chown=node app .
