## Build docker image
`docker build -t clo835-project-web .`

## Run container
`docker run -d -p 8080:80 clo835-project-web`

## Push image to docker hub
```
docker login
docker tag clo835-project-web trystan00000/clo835-project-web:latest
docker push trystan00000/clo835-project-web:latest
```
