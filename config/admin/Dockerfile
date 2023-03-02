FROM node:lts-alpine AS dependencies
WORKDIR /app

COPY ./package.json ./yarn.lock ./
COPY ./packages/admin ./packages/admin/

RUN yarn install
RUN yarn admin:install
RUN yarn admin:build

ENV NITRO_PORT=3030
EXPOSE 3030

CMD [ "yarn", "admin:start" ]