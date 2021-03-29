# Defines the tag for OBS and build script builds:
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%.%RELEASE%

FROM opensuse/tumbleweed

PREFIXEDLABEL org.opencontainers.image.title="Apache httpd container"
PREFIXEDLABEL org.opencontainers.image.description="Apache httpd container"
PREFIXEDLABEL org.opencontainers.image.created="%BUILDTIME%"
PREFIXEDLABEL org.opencontainers.image.version="%%PKG_VERSION%%.%RELEASE%"
PREFIXEDLABEL org.openbuildservice.disturl="%DISTURL%"
PREFIXEDLABEL org.opensuse.reference="registry.opensuse.org/opensuse/httpd:%%PKG_VERSION%%.%RELEASE%"

RUN zypper install -y --no-recommends httpd \
    zypper clean

# https://httpd.apache.org/docs/2.4/stopping.html#gracefulstop
STOPSIGNAL SIGWINCH

VOLUME /srv/www/htdocs

EXPOSE 80
ENTRYPOINT ["httpd", "-DFOREGROUND"]
