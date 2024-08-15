1. docker build -t express .
2. docker run -p 3000:3000 -d --mount type=bind,source=./src,target=/app express
3. docker stop 9b0c5f23c36e
4. docker rm 9b0c5f23c36
5. docker exec -it 9379c771d262 /bin/sh