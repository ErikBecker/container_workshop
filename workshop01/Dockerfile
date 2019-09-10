FROM node:latest

LABEL name="northwindapp" maintainer="ehbecker23@gmail.com"

### mydb image is require before build
ENV DB_HOST=mydb
ENV DB_PORT=3306
ENV APP_PORT=3000
ENV APP_DIR=/app 

WORKDIR ${APP_DIR}

### THE LAZY WAY
#ADD . .

### LONG WAY BUT BEST
ADD package.json .
ADD package-lock.json .
ADD main.js .
ADD config config
ADD public public
ADD views views

#INSTALL DEPENDENCY
RUN npm install

#expose the port 3000
EXPOSE ${APP_PORT}

#start the app
ENTRYPOINT [ "node", "main.js" ]