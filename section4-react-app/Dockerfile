FROM node:14.16.0-alpine3.13
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
COPY . .
# COPY ["hello world.txt" "."]
# ADD http://..../file.json .
# ADD will uncompress the zip
# ADD file.zip .
RUN npm install
ENV API_URL=https://api.myapp.com/
EXPOSE 3000
CMD npm start