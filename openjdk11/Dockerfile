# Defines the tag for OBS and build script builds:
#!BuildTag: opensuse/openjdk11:latest
#!BuildTag: opensuse/openjdk11:%%MINOR%%
#!BuildTag: opensuse/openjdk11:%%PKG_VERSION%%
#!BuildTag: opensuse/openjdk11:%%PKG_VERSION%%-%RELEASE%

FROM opensuse/tumbleweed

# labelprefix=org.opensuse.openjdk11
#PREFIXEDLABEL org.opencontainers.image.title="Openjdk11 container"
#PREFIXEDLABEL org.opencontainers.image.description="Openjdk11 container"
#PREFIXEDLABEL org.opencontainers.image.created="%BUILDTIME%"
#PREFIXEDLABEL org.opencontainers.image.version="%%PKG_VERSION%%-%RELEASE%"
#PREFIXEDLABEL org.opencontainers.image.vendor="openSUSE Project"
#PREFIXEDLABEL org.openbuildservice.disturl="%DISTURL%"
#PREFIXEDLABEL org.opensuse.reference="registry.opensuse.org/opensuse/openjdk11:%%PKG_VERSION%%-%RELEASE%"

# Just "plain" JDK (java+javac); might need some tweaking (TZ variable, locales, etc.)

RUN zypper install -y --no-recommends java-11-openjdk-devel && \
    zypper clean

RUN java -version && javac -version
