Locally built using

```console
docker buildx build . --tag registry.opensuse.org/openjdk:8
```

And tested using

```console
docker run -it <image_id> /bin/bash
java -version
javac -version
```
