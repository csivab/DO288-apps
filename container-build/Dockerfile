# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
EXPOSE 8080
LABEL io.k8s.description="Child Container" \
      io.k8s.display-name="A httpd child container" \
      io.openshift,expose-services="8080:http" \
      io.openshift.tags="httpd,Apache"
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && \
    sed -i "s/#Servername www.example.com/Servername 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf && \
    chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

USER ex288-sa

