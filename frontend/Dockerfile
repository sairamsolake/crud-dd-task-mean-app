# Build Angular
FROM node:20-alpine as builder

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

COPY . .

RUN npm run build -- --configuration production

# Serve with NGINX
FROM nginx:stable-alpine

COPY --from=builder /app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80
