FROM node:14

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install

# Copy app
COPY bin ./bin
COPY public ./public
COPY routes ./route
COPY views ./views
COPY app.js ./app.js

EXPOSE 3000

CMD [ "npm", "start" ]