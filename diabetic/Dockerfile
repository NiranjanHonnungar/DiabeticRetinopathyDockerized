FROM node:16 as build-step

WORKDIR /app

COPY ./package.json ./
COPY ./package-lock.json ./

COPY . .

RUN npm install
RUN npm run build

FROM nginx:stable-alpine
COPY --from=build-step /app/build /usr/share/nginx/html
COPY /nginx/nginx.conf /etc/nginx/conf.d/nginx.conf