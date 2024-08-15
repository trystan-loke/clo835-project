## Build docker image
`docker build -t clo835-project-service .`

## Run container
`docker run -d -p 3000:3000 clo835-project-service`

## Push image to docker hub
```
docker login
docker tag clo835-project-service trystan00000/clo835-project-service:latest
docker push trystan00000/clo835-project-service:latest
```
