FROM rockylinux:8
ENV JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto"
RUN yum -y install git \
 chkconfig \
 gnupg \
python3-pip \
wget   

RUN rpm --import https://yum.corretto.aws/corretto.key  &> /dev/null
RUN wget -qO-  https://yum.corretto.aws/corretto.repo | tee -a /etc/yum.repos.d/corretto.repo
RUN yum -y install java-11-amazon-corretto-devel  &> /dev/null
RUN mkdir -p /opt/thp/thehive/files
RUN rpm --import https://archives.strangebee.com/keys/strangebee.gpg 
ADD ./strangebee.repo /etc/yum.repos.d/strangebee.repo
RUN yum -y install thehive
RUN chown -R thehive:thehive /opt/thp/thehive/files
EXPOSE 9000