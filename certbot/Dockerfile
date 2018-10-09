FROM centos:7

LABEL maintainer daichi703n <daichi703n@gmail.com>

ENV EMAIL daichi703n@gmail.com
ENV DOMAINS *.herokuapp.com
ENV SERVER certbot.herokuapp.com

RUN yum install -y \
  epel-release
RUN yum install -y \
  nginx certbot certbot-apache
RUN yum clean all

EXPOSE 80 443

CMD bash -c "\
  nginx && \
  certbot certonly \
  --agree-tos \
  --webroot \
  --server https://$SERVER \
  -m $EMAIL \
  -d $DOMAINS"
