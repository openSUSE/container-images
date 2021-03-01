#!BuildTag: opensuse/samba

FROM opensuse/tumbleweed
LABEL maintainer="Bruno Leon <bruno.leon@suse.com>"

RUN zypper --non-interactive install catatonit timezone system-user-mail shadow samba

COPY entrypoint.sh /entrypoint.sh

EXPOSE 137/udp 138/udp 139 445

HEALTHCHECK --interval=60s --timeout=15s \
            CMD smbclient -L \\localhost -U % -m SMB3

ENTRYPOINT ["/usr/bin/catatonit", "--", "/entrypoint.sh"]

