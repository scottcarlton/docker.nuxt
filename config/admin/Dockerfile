# docker build -f ./config/admin/Dockerfile .
FROM node:lts-alpine AS dependencies
WORKDIR /app

COPY ./package.json ./yarn.lock ./
COPY ./packages/admin ./packages/admin/

RUN yarn install

# Build .output
RUN yarn admin:build

ENV NITRO_PORT=3030
ENV NITRO_PRESET=node-server

EXPOSE 3030

CMD ["node", "./packages/admin/.output/server/index.mjs"]

