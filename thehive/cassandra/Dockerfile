FROM rockylinux:8
ADD ./cassandra.repo /etc/yum.repos.d/cassandra.repo
RUN yum -y install cassandra
RUN chown -R cassandra:cassandra /etc/cassandra
EXPOSE 7000 9042
ENTRYPOINT [ "/etc/init.d/cassandra", "start" ]