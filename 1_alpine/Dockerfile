FROM node:10-alpine

EXPOSE 3000

RUN apk add --update curl

WORKDIR /usr/src
RUN mkdir app && chown -R node:node .
USER node
COPY --chown node:node package.json package-lock.json* ./
RUN npm install && npm cache clean --force
WORKDIR /usr/src/app
COPY --chown node:node . .

CMD ["node","app.js"]