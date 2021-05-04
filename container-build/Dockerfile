# Use the redhattraining/httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# Change the port to 8080
EXPOSE 8080

# Labels
LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
      io.k8s.display-name="Apache HTTP Server" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="apache, httpd"

# Configuracion de puertos
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

# Cambio de permisos
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

# Run as the root user
USER 1001
