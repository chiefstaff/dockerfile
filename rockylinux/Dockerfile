FROM scratch
ADD Rocky-8-Container-Base-8.7-20221113.0.x86_64.tar.xz /

LABEL org.rockylinux.name="RockyLinux Base Image" \
      org.rockylinux.build-date="20230207" \
      org.rockylinux.build-author="zhengwei"

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.aliyun.com/rockylinux|g' /etc/yum.repos.d/Rocky-*.repo; \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime;

CMD ["/bin/bash"]
