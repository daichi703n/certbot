FROM centos:7

LABEL maintainer daichi703n <daichi703n@gmail.com>

ENV EMAIL daichi703n@gmail.com
ENV DOMAINS *.herokuapp.com
ENV SERVER certbot.herokuapp.com
ENV PORT 5000

RUN yum install -y \
  epel-release
RUN yum install -y \
  certbot sudo
RUN yum clean all

#EXPOSE 80 443

USER root
#CMD echo "Hello world"
#CMD sudo certbot certonly \
CMD sudo certbot certonly \
  --agree-tos \
  --non-interactive \
  --standalone \
  --http-01-port $PORT \
  -m $EMAIL \
  -d $SERVER
