FROM node:lts-alpine3.17 as build
RUN mkdir -p /app

WORKDIR /app

COPY package.json /app/
RUN npm install

COPY . /app/
RUN npm run build --prod

FROM nginx:alpine
COPY --from=build /app/dist/moodle-el8laba-app /usr/share/nginx/html
