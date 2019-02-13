FROM alpine:3.9
RUN apk add gcc make musl-dev bash
COPY payload.c exploit.c Makefile pwn.sh /root/
WORKDIR /root
RUN make
ENTRYPOINT ["/root/pwn.sh"]
