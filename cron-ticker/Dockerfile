# /app  /usr /lib
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

#Comando run de la imagen
CMD ["node", "app.js"]