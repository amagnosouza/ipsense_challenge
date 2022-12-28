FROM node:16-buster-slim as build
WORKDIR /usr/src/app
COPY package*.json ./   
ENV NODE_ENV=production
RUN npm install
COPY . .

FROM node:16-alpine3.17
WORKDIR /app
COPY --from=build /usr/src/app /app
ENV NODE_ENV=production
CMD [ "npm", "start" ] npm start
EXPOSE 8081