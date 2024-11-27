# Execution:
Run ```vagrant up```

This will create the containers defined in the config.yaml file example below.

The `hashUrl` will set balance path dependant (in this exmaple also add the volumes to nginx)


```yaml
containers:
  echo:
    image: gcr.io/google_containers/echoserver:1.8
    replicaCount: 2
    port: 8080
    path: /api
  nginx:
    image: nginx:latest
    replicaCount: 2
    port: 80
    path: /statics
    hashUrl: true
    volumes:
      - /opt/nginx1/index.html:/usr/share/nginx/html/index.html