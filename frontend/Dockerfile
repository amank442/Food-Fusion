FROM node:18 AS build
WORKDIR /app
COPY frontend/package*.json ./
RUN npm install
COPY ./frontend .

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx","-g","daemon off;"]