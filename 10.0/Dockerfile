FROM odoo:10.0
MAINTAINER Lithin <lithint.mail@gmail.com>
USER root
#Inherted the exisitng Official Docker Image
# Mount /var/lib/odoo to allow restoring filestore and /opt/custom_addons for users addons
RUN mkdir -p /opt/custom_addons \
        && chown -R odoo /opt/custom_addons
VOLUME ["/var/lib/odoo", "/opt/custom_addons"]

# Expose Odoo services
EXPOSE 8069 8071

COPY ./odoo.conf /etc/odoo/odoo.conf

#Copy entrypoint script to container
COPY ./entrypoint.sh /

# Set default user when running the container
USER odoo

ENTRYPOINT ["/entrypoint.sh"]
CMD ["odoo"]
