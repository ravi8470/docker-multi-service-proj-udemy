FROM node:alpine
WORKDIR /app
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build



FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# Copy react build files to the location pointed by the nginx default.conf file
COPY --from=0 /app/build /usr/share/nginx/html