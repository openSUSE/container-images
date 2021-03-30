# Defines the tag for OBS and build script builds:
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%.%RELEASE%

FROM opensuse/tumbleweed

# labelprefix=org.opensuse.nano
PREFIXEDLABEL org.opencontainers.image.title="Example container"
PREFIXEDLABEL org.opencontainers.image.description="This contains nano"

RUN zypper install -y --no-recommends apache2 && \
    zypper clean

# https://httpd.apache.org/docs/2.4/stopping.html#gracefulstop
STOPSIGNAL SIGWINCH

VOLUME /srv/www/htdocs

EXPOSE 80
ENTRYPOINT ["httpd", "-DFOREGROUND"]
