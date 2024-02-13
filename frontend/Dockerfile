# Stage 1: Build environment
FROM node:14 AS build

WORKDIR /app

COPY ./package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Runtime environment
FROM nginx:latest

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
