# BUILDX
# docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t andresfon/cron-ticker:latest --push .

# /app  /usr /lib
# FROM --platform=linux/amd64 node:19.2-alpine3.16
# FROM --platform=$BUILDPLATFORM node:19.2-alpine3.16
FROM node:19.2-alpine3.16

# cd app
WORKDIR /app

#Destino /app
COPY package.json ./

#Instalar las dependencias
RUN npm install

#Destino /app
COPY . .

#Realizar testing
RUN npm run test

# Eliminar archivos y directorios no necesarios en PROD
RUN rm -rf tests && rm -rf node_modules

# Unicamente las dependencias de prod
RUN npm install --prod

#Comando run de la imagen
CMD ["node", "app.js"]