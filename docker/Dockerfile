FROM centos:8

# CentOSのリポジトリをVaultに変更
RUN sed -i 's|mirrorlist=|#mirrorlist=|g' /etc/yum.repos.d/CentOS-Linux-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=https://vault.centos.org|g' /etc/yum.repos.d/CentOS-Linux-* && \
    dnf --setopt=sslverify=false -y update && \
    dnf clean all && \
    dnf --setopt=sslverify=false -y install nginx

CMD ["nginx", "-g", "daemon off;"]
