# Image Base
FROM node:alpine

WORKDIR /app
# Dependencies
# RUN apk add --update nodejs npm
COPY ./package.json ./
RUN npm install
COPY ./ ./

# Startup config
CMD ["npm", "run", "start"]
