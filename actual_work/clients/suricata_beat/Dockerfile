FROM jasonish/suricata

RUN rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch
COPY ./elastic.repo /etc/yum.repos.d/
RUN yum update -y
RUN yum install filebeat -y
RUN systemctl enable filebeat
RUN filebeat modules enable suricata

