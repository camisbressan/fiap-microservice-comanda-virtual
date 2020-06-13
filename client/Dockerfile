# build environment
FROM node:13-alpine as build
WORKDIR /client
ENV PATH /client/node_modules/.bin:$PATH
COPY package.json /client/package.json
RUN npm install --silent
RUN npm install react-scripts@3.3.1 -g --silent
COPY . /client
RUN npm run build
# production environment
FROM nginx:1.16.0-alpine
COPY -- from=build /client/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g" , "daemon off;"]