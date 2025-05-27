FROM node:18-alpine AS ionic
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install -g @ionic/cli && npm ci
COPY . .
RUN ionic build

FROM nginx:alpine
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html