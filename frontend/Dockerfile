FROM node:14-alpine3.15
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "start"]

# For Deploying in NGINX which is a Multistage-Dockerfile

# FROM node:14-alpine3.15 AS builder
# RUN apk update
# WORKDIR /app
# COPY package*.json ./
# RUN npm install
# COPY . .
# RUN npm run build

# FROM nginx:alpine
# RUN apk update
# COPY --from=builder /app/build /usr/share/nginx/html
# COPY default.conf /etc/nginx/conf.d/default.conf
# CMD ["nginx", "-g", "daemon off;"]