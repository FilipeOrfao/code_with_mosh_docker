FROM node:14.16.0-alpine3.13
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
# COPY --chown=app package.json . 
COPY package.json . 
USER root 
RUN mkdir data
RUN npm install
# USER app
# COPY --chown=app . .
COPY . .
ENV API_URL=http://api.myapp.com/
EXPOSE 3000
CMD ["npm", "start"]



