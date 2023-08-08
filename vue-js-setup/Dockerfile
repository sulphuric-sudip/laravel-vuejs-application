# build stage
FROM node:19.5.0-alpine as build-stage

WORKDIR /app

COPY ./vue-js-app/package*.json ./

RUN npm install

COPY ./vue-js-app/ .

RUN npm run build


# production stage
FROM nginx:stable-alpine as production-stage

# the files are created in previous build stage and copied to the nginx html folder
COPY --from=build-stage /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]