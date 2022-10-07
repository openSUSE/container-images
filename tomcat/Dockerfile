# Defines the tag for OBS and build script builds:
#!BuildTag: opensuse/tomcat:latest
#!BuildTag: opensuse/tomcat:%%MINOR%%
#!BuildTag: opensuse/tomcat:%%PKG_VERSION%%
#!BuildTag: opensuse/tomcat:%%PKG_VERSION%%-%RELEASE%

FROM opensuse/tumbleweed

# labelprefix=org.opensuse.tomcat
LABEL org.opencontainers.image.title="Apache tomcat container"
LABEL org.opencontainers.image.description="Apache tomcat container"
LABEL org.opencontainers.image.created="%BUILDTIME%"
LABEL org.opencontainers.image.version="%%PKG_VERSION%%-%RELEASE%"
LABEL org.opencontainers.image.vendor="openSUSE Project"
LABEL org.openbuildservice.disturl="%DISTURL%"
LABEL org.opensuse.reference="registry.opensuse.org/opensuse/tomcat:%%PKG_VERSION%%-%RELEASE%"
# endlabelprefix

RUN zypper install -y --no-recommends tomcat && \
    zypper clean

USER tomcat

EXPOSE 8080
ENTRYPOINT ["/usr/libexec/tomcat/server", "start"]
