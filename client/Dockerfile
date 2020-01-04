## Phase 1
# Image Base
FROM node:alpine AS builder

WORKDIR /app

# Dependencies
# RUN apk add --update nodejs npm
COPY ./package.json ./
RUN npm install
COPY ./ ./
# Startup config
RUN ["npm", "run", "build"]

## Phase 2
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
