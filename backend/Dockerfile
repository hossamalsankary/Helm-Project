FROM node:11.0.0-alpine 


WORKDIR /usr/src/app

ENV NODE_ENV=local
ENV VERSION=1
ENV TYPEORM_CONNECTION=postgres
ENV TYPEORM_MIGRATIONS_DIR=./src/migrations
ENV TYPEORM_ENTITIES=./src/modules/domain/**/*.entity.ts
ENV TYPEORM_MIGRATIONS=./src/migrations/*.ts

ENV TYPEORM_HOST=localhost
ENV TYPEORM_PORT=5532
ENV TYPEORM_USERNAME=postgres
ENV TYPEORM_PASSWORD=password
ENV TYPEORM_DATABASE=glee

COPY package*.json ./

RUN npm install

COPY . .


RUN npm run build 

WORKDIR /usr/src/backend




CMD ["node" , "./dist/main.js"]

