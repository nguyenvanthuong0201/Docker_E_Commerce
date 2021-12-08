# # Install Node Image
# FROM node:12.2.0-alpine as client

# # Working directory inside the container
# WORKDIR /app

# ENV PATH /app/node_modules/.bin:$PATH

# # Copy over the package.json files
# COPY ./package*.json /app/

# # Install dependencies
# RUN npm install --silent

# RUN npm install react-scripts -g --silent

# # Copy everything
# COPY . .

# # Build the application
# RUN npm run build

# # Build nginx server
# FROM nginx:latest

# EXPOSE 80

# # Copy all the contents from the build directory into the web root
# COPY --from=client /app/build/ /var/www/html

# COPY ./nginx/default.conf /etc/nginx/conf.d

# CMD ["nginx", "-g", "daemon off;"]


FROM node:12.18.3

LABEL version="1.0"
LABEL description="This is the base docker image for the Tweet Sentiment Analysis frontend react app."

WORKDIR /app

COPY ["package.json", "package-lock.json", "./"]

RUN npm install --production

COPY . .

EXPOSE 3000

CMD ["npm", "start"]