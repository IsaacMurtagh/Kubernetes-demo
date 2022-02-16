FROM node:14
WORKDIR /app
COPY package.json /app
RUN npm install
COPY ./src /app
CMD yarn start
EXPOSE 3000