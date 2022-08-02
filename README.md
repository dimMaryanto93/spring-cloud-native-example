# SpringBoot native-image

Build springboot project for native-image using GraalVM

## System required

- Install GraalVM and set `gu` to path
- Install docker-engine or Docker Desktop
- Add resource to docker engine / docker VM with
  - Minimum memory: `4GB`
  - Minimum CPUs: `4cores`
  - Minimum storage: `24GB`

## Build command

Run development:

```bash
mvn clean spring-boot:run
```

Run build for production:

```bash
mvn clean spring-boot:build-image

# using docker
docker run -d --name backend -p 8080:8080 dimmaryanto93/spring-cloud-native-example:0.0.1-SNAPSHOT

# using kubernetes
kubectl create deploy backend --image dimmaryanto93/spring-cloud-native-example:0.0.1-SNAPSHOT --port 8080

kubectl expose deploy/backend --port 8080 --type=NodePort
```
