# What is this image ?

The Tomcat Server

This is a simple tomcat container based on openSUSE Tumbleweed

# Source or Package ?

This image build on openSUSE RPM package.

It does not rebuild tomcat from source as does the "official" community image
because openSUSE Tumbleweed continuously ships a very recent version.

# Usage

### Without a `Dockerfile`

If you don't want to include a `Dockerfile` in your project, it is sufficient to do the following:

```console
$ podman run -dit --name my-tomcat-app -p 8080:80 -v "$PWD"/app:/srv/tomcat/webapps registry.opensuse.org/tomcat:9
```

### Configuration

To customize the configuration, you should most likely add a config file to
container's /etc/tomcat/conf.d/ folder.

That is you should mount it as a volume or rebuild the container:

```console
$ podman run -dit --name my-tomcat-app -p 8080:8080 -v "$PWD/config":/etc/tomcat/conf.d/ -v "$PWD/app":/srv/tomcat/webapps registry.opensuse.org/tomcat:9
```
