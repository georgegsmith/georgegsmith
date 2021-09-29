# George's Notes

## Localstack 
Localstack can be invoked from a powershell command line using docker in one of two ways 

Using a docker yaml file like this: 

```
version: "3.8"

services:
  localstack:
    container_name: "${LOCALSTACK_DOCKER_NAME-localstack_main}"
    image: localstack/localstack
    network_mode: bridge
    ports:
      - "127.0.0.1:63:63"
      - "127.0.0.1:63:63/udp"
      - "127.0.0.1:443:443"
      - "127.0.0.1:4566:4566"
      - "127.0.0.1:4571:4571"
    environment:
      - SERVICES=${SERVICES- }
      - DEBUG=${DEBUG- }
      - DATA_DIR=${DATA_DIR- }
      - LAMBDA_EXECUTOR=${LAMBDA_EXECUTOR- }
      - LOCALSTACK_API_KEY=5tj8pBsWQ4
      - KINESIS_ERROR_PROBABILITY=${KINESIS_ERROR_PROBABILITY- }
      - DOCKER_HOST=unix:///var/run/docker.sock
      - HOST_TMP_FOLDER="${TMPDIR:-/tmp}/localstack"
    volumes:
      - "${TMPDIR:-/tmp}/localstack:/tmp/localstack"
      - "/var/run/docker.sock:/var/run/docker.sock"
```
and then running the command from the command line (requires docker-compose install

`docker-compose up`

or invoking directly from the command like like this 

`docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack`

To check that all the Localstack services are running go here 

`http://localhost:4566/health` 

Localhost also has a UI which looks like this 

![title](/images/localstack.PNG)




## Docker 


## Powershell

