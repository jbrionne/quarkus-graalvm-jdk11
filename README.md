# Quarkus getting-started project with native image build and docker


## Build and execute with a docker multistage

```
docker build -f src/main/docker/Dockerfile.multistage -t quarkus-quickstart/getting-started .
```

```
docker run -i --rm -p 8080:8080 quarkus-quickstart/getting-started
```


Test

```
curl -w "\n" http://localhost:8080/hello/greeting/quarkus
```

Well done, you have a docker with a native application !


## Dev


```
mvn compile quarkus:dev
```


## Local Graalvm

Only if you don't want to use docker !

Install Graalvm and :

```
mvn package -Pnative
```

Execute the application build:

```
target/quarkus-graalvm-jdk11-1.0.0-SNAPSHOT-runner
```

Test with the same curl command.
