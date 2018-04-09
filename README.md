# How to run re-create docker image

**mvn clean package docker:build**

# To run image

## Create network

**docker network create ms-net**

## Run image

**docker run
  -p 5555:5555
  --env PROFILE=dev
  --env CONFIGSERVER_PORT=8888
  --env CONFIGSERVER_URI=http://ms-confserver:8888
  --env ENCRYPT_KEY=\*\*\*\*\*\*
  --env EUREKASERVER_PORT=8761
  --env EUREKASERVER_URI=http://ms-eureka:8761/eureka/
  --env SERVER_PORT=5555
  --env ZIPKIN_PORT=9411
  --env ZIPKIN_URI=http://ms-zipkin:9411
  --name ms-gateway
  --network ms-net
  tesei7/ms-gateway:latest**