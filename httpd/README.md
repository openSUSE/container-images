# What is this image ?

The Apache HTTP Server

This is a simple httpd container based on openSUSE Tumbleweed

This README is inspired from https://github.com/docker-library/docs/blob/master/httpd/README.md

# Source or Package ?

This image build on openSUSE RPM package.

It does not rebuild httpd from source as does the "official" community image
because openSUSE Tumbleweed continuously ships a very recent version.

# Usage

### Without a `Dockerfile`

If you don't want to include a `Dockerfile` in your project, it is sufficient to do the following:

```console
$ podman run -dit --name my-apache-app -p 8080:80 -v "$PWD":/srv/www/htdocs/ registry.opensuse.org/httpd:2.4
```

### Configuration

To customize the configuration of the httpd server, you should most likely add a config file to
container's /etc/apache2/conf.d folder.

That is you should mount it as a volume or rebuild the container:

```console
$ podman run -dit --name my-apache-app -p 80:80 -v "$PWD/config":/etc/apache2/conf.d/ -v "$PWD/site":/srv/www/htdocs/ registry.opensuse.org/httpd:2.4
```
