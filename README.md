# code-with-quarkus Project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## 1. Getting started
### 1.1 Prerequisites
It is assumed that you have basic software tools such as `git`, `java`, `gradle`. Ideally you would have [SDKMAN](https://sdkman.io) installed and all the tools would download themselves, based on instructions provided inside of [.sdkmanrc](./.sdkmanrc) file.  
If you don't have [SDKMAN](https://sdkman.io), it is not the end of the world. You should be able to start the project with your tools as well.  
### 1.2. Download project
Clone source code into destination of your choice:
```shell script
git clone git@github.com:ochmanskide/quarkus.code-with-quarkus.git ~/Workspace/02-github/ochmanskide/quarkus/code-with-quarkus
```

## 2. Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
gradle quarkusDev
```
if you have `quarkus` installed you may simply run:
```shell script
quarkus dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
gradle build -x test
```
It produces the `quarkus-run.jar` file in the `./build/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `./build/quarkus-app/lib/` directory.

The application is now runnable using `java -jar ./build/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:
```shell script
gradle build -x test -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar ./build/code-with-quarkus-*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
gradle build -x test -Dquarkus.package.type=native
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
gradle build -x test -Dquarkus.package.type=native -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./build/libs/code-with-quarkus-1.0.0-SNAPSHOT-runner`

## Related Guides

- RESTEasy Classic ([guide](https://quarkus.io/guides/resteasy)): REST endpoint framework implementing JAX-RS and more

## Provided Code

### RESTEasy JAX-RS

Easily start your RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started#the-jax-rs-resources)
