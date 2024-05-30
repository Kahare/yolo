# Stage 1: Build the apllication(using multi stage builds)
FROM node:14-alpine AS build 

WORKDIR /client/app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

#Stage 2:Serve the application
FROM node:14-alpine as main 

WORKDIR /client/app

COPY --from=build /client/app/. .

EXPOSE 3000

CMD ["npm", "start"]
