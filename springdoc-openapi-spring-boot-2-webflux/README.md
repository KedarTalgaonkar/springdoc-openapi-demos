# springdoc-openapi demo with spring-boot-2 web-flux

## Building application

### Pre-requisites
- JDK 8+
- maven 3
- docker CLI

### Option 1: Building Executable JAR
To create an `executable jar`, simply run:

```sh
 mvn clean package
```

### Option 2: Building a non-native OCI Images
To create a non-native OCI docker image, simply run:

```sh
mvn clean spring-boot:build-image
```

### Option 3: Building native image with GraalVM
To create a `native image`, the project rely on spring-native project and buildpacks.
Run the following command

```sh
mvn -Pnative-image clean spring-boot:build-image
```

## Running the native application

To run the demo using docker, invoke the following:

```sh
docker pull springdocdemos/springdoc-openapi-spring-boot-2-webflux:latest
docker run --rm -p 8080:8080 springdocdemos/springdoc-openapi-spring-boot-2-webflux:latest
```

DOCKER_BUILDKIT=1 docker build -t springdoc-openapi-spring-boot-2-webflux -f springdoc-openapi-spring-boot-2-webflux/Dockerfile .


docker run --rm -d --privileged -p 8081:8080 springdoc-openapi-spring-boot-2-webflux:latest

docker run springdoc-openapi-spring-boot-2-webflux 