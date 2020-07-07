FROM node:alpine

WORKDIR '/my-app'

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx
EXPOSE 80
COPY --from=0 /my-app/build /usr/share/nginx/html