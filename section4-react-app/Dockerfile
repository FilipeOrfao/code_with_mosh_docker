FROM node:14.16.0-alpine3.13
RUN addgroup app && adduser -S -G app app
WORKDIR /app
COPY package*.json .
# COPY ["hello world.txt" "."]
# ADD http://..../file.json .
# ADD will uncompress the zip
# ADD file.zip .
RUN npm install
COPY . .
ENV API_URL=https://api.myapp.com/
EXPOSE 3000
#shell form 
# CMD npm start
# exec form
USER app
CMD ["npm", "start"]
# ENTRYPOINT [ "npm", "start" ]



