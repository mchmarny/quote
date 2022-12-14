# Welcome to the Maven demo app!

This is a Maven quote rotation sample application courtesy of [ddobrin](https://github.com/ddobrin). It can be built locally, in docker, and run in Docker, Kubernetes, or Cloud Run. It includes skaffold.yaml and Cloud Build files to build automatically.

## Local build Pre-requisites

1. Install [Eclipse-Temurin 17](https://adoptium.net/installation/) in the local build environment
2. Install [Maven 3](https://maven.apache.org/install.html) in the local build environment

## Integration test with Maven

1. Ensure a local docker environment is running
2. Next, in the root of this depo, run:

```bash
mvn verify
```

## Maven package

1. Ensure a local docker environment is running
2. Next, in the root of this depo, run:

```bash
mvn package
```

## Docker build

After packaging locally, you can run docker build to create a container.

```bash
docker build . -t $REGION-docker.pkg.dev/$PROJECT_ID/$REGISTRY/quote
```
## Docker run

```bash
docker run $REGION-docker.pkg.dev/$PROJECT_ID/$REGISTRY/quote
```

## Docker push

```bash
docker push $REGION-docker.pkg.dev/$PROJECT_ID/$REGISTRY/quote
```

## Continuous development with Skaffold

1. Ensure a local docker environment is running
2. Navigate to the root directory of the repo
3. Customize command below for your project and repo, and run:

```bash
skaffold dev --default-repo=$REGION-docker.pkg.dev/$PROJECT_ID/$REGISTRY/quote
```
