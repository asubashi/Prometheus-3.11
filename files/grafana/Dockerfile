# Dockerfile
FROM registry.access.redhat.com/rhel7.4
USER root
EXPOSE 3000

ENV GRAFANA_VERSION="5.0.3" \
    GRAFANA_BUILD="1"


ADD root /
RUN curl -L -o grafana-${GRAFANA_VERSION}-${GRAFANA_BUILD}.x86_64.rpm  https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-${GRAFANA_VERSION}-${GRAFANA_BUILD}.x86_64.rpm  && \
    yum -y  install grafana-${GRAFANA_VERSION}-${GRAFANA_BUILD}.x86_64.rpm && yum clean all


COPY run.sh /usr/share/grafana/
RUN chmod +x /usr/bin/fix-permissions && chmod +x /usr/share/grafana/run.sh

RUN /usr/bin/fix-permissions /usr/share/grafana \
    && /usr/bin/fix-permissions /etc/grafana \
    && /usr/bin/fix-permissions /var/lib/grafana \
    && /usr/bin/fix-permissions /var/log/grafana

WORKDIR /usr/share/grafana
ENTRYPOINT ["./run.sh"]
