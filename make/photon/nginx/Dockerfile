FROM vmware/photon:1.0

RUN tdnf distro-sync -y \
    && tdnf install -y nginx \
    && ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log \
    && tdnf clean all

EXPOSE 80
VOLUME /var/cache/nginx /var/log/nginx /run
STOPSIGNAL SIGQUIT

CMD ["nginx", "-g", "daemon off;"]
