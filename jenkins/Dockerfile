FROM jenkins/jenkins:2.375.3-slim

LABEL jenkins.image.build-time="20230217" \
      jenkins.image.version="2.375.3" \
	  jenkins.image.author="zhengwei"

USER root

RUN sed -i "s@http://deb.debian.org@https://mirrors.aliyun.com@g" /etc/apt/sources.list; \
    apt-get -y install apt-transport-https ca-certificates && apt-get -y update; \
    ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime;

# docker
RUN apt-get -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common; \
    curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg; \
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://mirrors.aliyun.com/docker-ce/linux/debian $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null; \
    apt-get -y update && apt-get -y install docker-ce;


# kubectl
RUN curl -fsSL https://mirrors.aliyun.com/kubernetes/apt/doc/apt-key.gpg | gpg --dearmor -o /etc/apt/keyrings/kubernetes.gpg; \
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/kubernetes.gpg] https://mirrors.aliyun.com/kubernetes/apt/ kubernetes-xenial main" | tee /etc/apt/sources.list.d/kubernetes.list > /dev/null; \
	apt-get -y update && apt-get -y install kubectl; \
	apt-get -y clean;