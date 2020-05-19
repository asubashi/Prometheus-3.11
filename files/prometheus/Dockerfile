FROM registry.access.redhat.com/openshift3/prometheus:v3.7.23

MAINTAINER Bahaddin Cankurt <bahaddin.cankurt@lhind.dlh.de>

VOLUME     [ "/prometheus" ]
WORKDIR    /prometheus
ENTRYPOINT [ "/bin/prometheus" ]
CMD        [ "--config.file=/prometheus-config/prometheus-config.yml", \
             "--storage.tsdb.path=/prometheus",\
             "--web.console.libraries=/usr/share/prometheus/console_libraries",\
             "--web.console.templates=/usr/share/prometheus/consoles",\
             "--storage.tsdb.retention=15d" ]
