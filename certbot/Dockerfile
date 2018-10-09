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

#EXPOSE 80 443

ENV PORT 5000

#CMD echo "Hello world"
CMD certbot certonly \
  --work-dir /tmp \
  --logs-dir /tmp/logs \
  --agree-tos \
  --non-interactive \
  --standalone \
  --http-01-port $PORT \
  -m $EMAIL \
  -d $SERVER
