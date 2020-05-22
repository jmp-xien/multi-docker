# Use base image
FROM node:alpine

WORKDIR '/app'

#  LOCAL   CONTAINER
COPY ./package.json ./
RUN npm install
COPY ./ ./

CMD ["npm", "run", "start"]

