# Use base image
FROM node:alpine as builder
WORKDIR '/app'

#  LOCAL   CONTAINER
COPY package*.json ./
RUN npm install

COPY ./ ./
# CMD ["npm", "run", "start"]
RUN npm run build

# New Image
FROM nginx
EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
