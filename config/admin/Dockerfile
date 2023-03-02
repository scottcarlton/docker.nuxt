FROM node:lts-alpine AS dependencies
WORKDIR /app

COPY ../../package.json ./
# COPY ../../yarn.lock ./

RUN yarn install

# COPY ./packages/admin ./packages/admin/

RUN yarn admin:install

RUN yarn admin:build

EXPOSE 3030

CMD [ "yarn", "admin:start" ]