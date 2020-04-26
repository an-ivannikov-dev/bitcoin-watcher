FROM node:lts

ENV DATA_DIR=/data \
    ENV=production \
    NODE_ENV=production

WORKDIR /app

COPY ["package.json", "yarn.lock", "./"]
RUN yarn install --production --silent && mv node_modules ../
COPY . .
RUN rm -R docker && mkdir /data

RUN PATH=${PATH}:/app/bin
EXPOSE 80 443
VOLUME ["/data"]

CMD ["yarn" "run" "start:prod"]
