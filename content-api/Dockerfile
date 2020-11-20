FROM node:alpine AS baseRUN apk -U add curlWORKDIR /usr/src/appEXPOSE 3001
FROM node:argon AS buildWORKDIR /usr/src/app
# Install app dependenciesCOPY package.json /usr/src/app/RUN npm install
# Bundle app sourceCOPY . /usr/src/app
FROM base AS finalWORKDIR /usr/src/appCOPY --from=build /usr/src/app .CMD [ "npm", "start" ]
