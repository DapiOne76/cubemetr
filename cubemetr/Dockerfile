FROM node:10-alpine

ENV APP_ROOT /src

RUN mkdir ${APP_ROOT}
WORKDIR ${APP_ROOT}
ADD . ${APP_ROOT}

RUN npm install
RUN npm rebuild node-sass --force
RUN npm run build

ENV HOST 0.0.0.0
