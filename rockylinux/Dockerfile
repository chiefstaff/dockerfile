FROM scratch

LABEL com.chnstack.name="RockyLinux Base Image" \
      com.chnstack.build-date="20230719" \
      com.chnstack.build-author="zhengwei" \
      com.chnstack.osversion="8"

#ADD Rocky-8-Container-Base-8.7-20221113.0.x86_64.tar.xz /
ADD https://mirrors.aliyun.com/rockylinux/8/images/x86_64/Rocky-8-Container-Base.latest.x86_64.tar.xz /

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.aliyun.com/rockylinux|g' /etc/yum.repos.d/Rocky-*.repo; \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime;

CMD ["/bin/bash"]
