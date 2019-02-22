FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install subversion sasl2-bin -y && \
    mkdir -p /etc/sasl && \
    chmod 744 /etc/sasl

COPY *.conf /etc/sasl

VOLUME ["/home/svn"]

EXPOSE 3690

ENTRYPOINT ["/usr/bin/svnserve","--foreground", "-d", "-r", "/home/svn/repo"]