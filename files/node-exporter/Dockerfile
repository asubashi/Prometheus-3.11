FROM registry.access.redhat.com/rhel7.5

MAINTAINER  <subashi@scigames>

# node_exporter releases:
# https://github.com/prometheus/node_exporter/releases

RUN \
  curl -L -o node_exporter-1.0.0-rc.1.linux-amd64.tar.gz \
    https://github.com/prometheus/node_exporter/releases/tag/v1.0.0-rc.1/node_exporter-1.0.0-rc.1.linux-amd64.tar.gz && \
  tar -zxvf node_exporter-1.0.0-rc.1.linux-amd64.tar.gz -C /tmp/ && \
  rm node_exporter-1.0.0-rc.1.linux-amd64.tar.gz

RUN mv /tmp/node_exporter-1.0.0-rc.1.linux-amd64/node_exporter /usr/bin/node_exporter
RUN chmod a+x /usr/bin/node_exporter

EXPOSE  9100
ENTRYPOINT  [ "/usr/bin/node_exporter" ]
