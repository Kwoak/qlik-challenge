FROM --platform=linux/arm64 node:20.15-alpine

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

USER node

WORKDIR /home/node/app

COPY --chown=node:node package.json .
COPY --chown=node:node package-lock.json .

RUN npm install

COPY --chown=node:node . .

EXPOSE 9091

CMD [ "node", "server.js" ]