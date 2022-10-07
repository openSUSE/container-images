# Defines the tag for OBS and build script builds:
#!BuildTag: opensuse/httpd:latest
#!BuildTag: opensuse/httpd:%%MINOR%%
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%
#!BuildTag: opensuse/httpd:%%PKG_VERSION%%-%RELEASE%

FROM opensuse/tumbleweed

# labelprefix=org.opensuse.httpd
LABEL org.opencontainers.image.title="Apache httpd container"
LABEL org.opencontainers.image.description="Apache httpd container"
LABEL org.opencontainers.image.created="%BUILDTIME%"
LABEL org.opencontainers.image.version="%%PKG_VERSION%%-%RELEASE%"
LABEL org.opencontainers.image.vendor="openSUSE Project"
LABEL org.openbuildservice.disturl="%DISTURL%"
LABEL org.opensuse.reference="registry.opensuse.org/opensuse/httpd:%%PKG_VERSION%%-%RELEASE%"
# endlabelprefix

RUN zypper install -y --no-recommends apache2 && \
    zypper clean

# https://httpd.apache.org/docs/2.4/stopping.html#gracefulstop
STOPSIGNAL SIGWINCH

VOLUME /srv/www/htdocs

EXPOSE 80
ENTRYPOINT ["httpd", "-DFOREGROUND"]
