FROM jenkins/jenkins
USER root
RUN apt-get update -y && apt-get install -y apt-transport-https wget curl ca-certificates software-properties-common 
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add 
ADD kubernetes.list /etc/apt/sources.list.d/kubernetes.list
RUN apt-get update -y && apt-get install kubectl
RUN /usr/local/bin/install-plugins.sh kubernetes
RUN  /usr/local/bin/install-plugins.sh kubernetes-cli
RUN  /usr/local/bin/install-plugins.sh git
RUN  /usr/local/bin/install-plugins.sh git-client
RUN apt-get install -y docker-engine
RUN usermod -a -G docker jenkins



