#build singa from dev-base
FROM singa/mesos
MAINTAINER Anh Dinh<ug93tad@gmail.com>

COPY hdfs-site.xml /opt/hadoop-2.6.0/etc/hadoop/
COPY hdfs-client.xml /opt/hadoop-2.6.0/etc/hadoop/
COPY .bashrc /root/

RUN source ~/.bashrc && cd && mkdir singa-97 && cd singa-97 && git clone https://github.com/ug93tad/incubator-singa && cd incubator-singa && git checkout SINGA-97 && ./autogen.sh && ./configure && make && cd examples/cifar10 && cp Makefile.example Makefile && make compile && cp -r /root/incubator-singa/examples/cifar10/cifar-10-batches-bin .

COPY job.conf /root/singa-97/incubator-singa/examples/cifar10/
COPY singa.conf /root/singa-97/incubator-singa/conf/ 
