version: '3.8'

services:
  mysql-db:
    image: mysql:8.0
    container_name: mysql-db
    environment:
      MYSQL_ROOT_PASSWORD: Root@123
      MYSQL_DATABASE: tododb
    ports:
      - "3307:3306"
    volumes:
      - mysql-data:/var/lib/mysql
    networks:
      - todo-network

  todo-application:
    image: todo-application-image:latest
    container_name: todo-application
    depends_on:
      - mysql-db
    ports:
      - "8082:8081"
    networks:
      - todo-network

networks:
  todo-network:
    driver: bridge

volumes:
  mysql-data:
