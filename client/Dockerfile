FROM  node:16-alpine

WORKDIR /app

COPY ./package.json ./

RUN npm install

COPY  . . 

RUN npm run build

EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/conf.d/default.config
COPY --from=bulder /app/build/ /usr/share/nginx