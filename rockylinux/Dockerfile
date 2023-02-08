FROM scratch
ADD Rocky-8-Container-Minimal-8.7-20221112.0.x86_64.tar.xz /

LABEL org.rockylinux.name="RockyLinux Base Image" \
      org.rockylinux.build-date="20230207" \
      org.rockylinux.build-author="zhengwei"

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' \
    -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.aliyun.com/rockylinux|g' \
    -i.bak \
    /etc/yum.repos.d/Rocky-*.repo

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime	

CMD ["/bin/bash"]
