FROM alpine:3.22

RUN apk add --no-cache \
    bash \
    bind-tools \
    iptables \
    ip6tables \
    openvpn \
    tinyproxy

COPY . /usr/local/bin
RUN mv /usr/local/bin/tinyproxy.conf /etc/tinyproxy/tinyproxy.conf

ENV KILL_SWITCH=on

ENTRYPOINT [ "entry.sh" ]
