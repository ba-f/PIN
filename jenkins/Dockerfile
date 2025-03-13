FROM jenkins/jenkins:lts-jdk17

USER root

RUN apt-get update && apt-get install -y \
apt-transport-https \
ca-certificates \
curl \
gnupg2 \
software-properties-common \
lsb-release \
&& rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y docker.io && rm -rf /var/lib/apt/lists/*

RUN usermod -aG docker jenkins

USER jenkins

EXPOSE 8080

ENTRYPOINT [ "/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh" ]