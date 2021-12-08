#Docker
#Create folder
ex: Docker
#Ceate file : docker-compose.yml
#Write :

version: '3'
services:
  backend:
    image: "thuong0201/ecommerce-backend"
    ports:
      - "4000:4000"
  frontend:
    image: "thuong0201/ecommerce-frontend"
    ports:
      - "3000:3000"
    links:
      - "backend"

# Commandline
docker-compose up -d
