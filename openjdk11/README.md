Locally built using

```console
docker buildx build . --tag registry.opensuse.org/openjdk:11
```

And tested using

```console
docker run -it <image_id> /bin/bash
java -version
javac -version
```
