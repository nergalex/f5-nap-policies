# source: https://docs.nginx.com/nginx-app-protect/admin-guide/install/
# For CentOS 7:
FROM centos:7.4.1708

# Download certificate and key from the customer portal (https://my.f5.com)
# and copy to the build context:
COPY nginx-repo.crt nginx-repo.key /etc/ssl/nginx/

# Install prerequisite packages:
RUN yum -y install wget ca-certificates epel-release

# Add NGINX Plus repo to Yum:
RUN wget -P /etc/yum.repos.d https://cs.nginx.com/static/files/nginx-plus-7.repo

# Update the repository and install the most recent version of the NGINX App Protect Compiler package:
RUN yum -y install app-protect-compiler \
    && yum clean all \
    && rm -rf /var/cache/yum \
    && rm -rf /etc/ssl/nginx

CMD ["sh"]