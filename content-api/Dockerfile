FROM node:alpine AS base
RUN apk -U add curl
WORKDIR /usr/src/appEXPOSE 3001
FROM node:argon AS build
WORKDIR /usr/src/app
# Install app dependenciesCOPY package.json /usr/src/app/RUN npm install
# Bundle app sourceCOPY . /usr/src/app
FROM base AS final
WORKDIR /usr/src/app
COPY --from=build /usr/src/app .
CMD [ "npm", "start" ]
