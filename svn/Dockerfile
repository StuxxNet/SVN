FROM centos:7

RUN yum update -y && \
    yum install cyrus-sasl cyrus-sasl-md5 cyrus-sasl-lib cyrus-sasl-sql cyrus-sasl-plain subversion wget -y
COPY *.conf /etc/sasl2

VOLUME ["/home/svn", "/home/database"]

EXPOSE 3690

ENTRYPOINT ["/usr/bin/svnserve","--foreground", "-d", "-r", "/home/svn"]