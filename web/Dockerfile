FROM node:16-buster-slim as build
ENV NODE_ENV=production
WORKDIR /usr/src/app
COPY package*.json ./   
RUN npm install
COPY . .

FROM node:16-alpine3.17
ENV NODE_ENV=production
WORKDIR /app
COPY --from=build /usr/src/app /app
CMD [ "npm", "start" ] npm start
EXPOSE 8080