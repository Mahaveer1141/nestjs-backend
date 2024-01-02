FROM node:19-alpine

RUN apk update && apk upgrade && apk add bash
RUN mkdir app

WORKDIR /app

COPY package.json .
COPY yarn.lock .

RUN yarn

COPY . .

RUN npx prisma generate

CMD [ "yarn", "start:dev" ]

EXPOSE 3000
