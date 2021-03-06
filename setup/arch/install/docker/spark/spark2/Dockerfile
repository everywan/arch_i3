FROM centos

MAINTAINER wzs

# 安装sshd
RUN yum install -y openssh-server
# 将sshd的UsePAM参数设置成no 
RUN sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key

# 添加测试用户root, 密码root, 并且将此用户添加到sudoers里  
RUN echo "root:root" | chpasswd  
RUN echo "root   ALL=(ALL)       ALL" >> /etc/sudoers

RUN echo "export TERM=linux" >> /root/.bashrc
RUN echo "export TERM=xterm-256color" >> /root/.bashrc
RUN echo "alias ll='ls -l'" >> /root/.bashrc

# 启动sshd服务并且暴露22端口  
RUN mkdir /var/run/sshd  
EXPOSE 22  
CMD ["/usr/sbin/sshd", "-D"]

# 安装&配置jdk
RUN yum install -y java-1.8.0-openjdk.x86_64

# 安装&配置python2
RUN yum install -y python2
RUN ln -s /usr/bin/python2 /usr/bin/python

# 安装&配置spark
ADD spark-2.2.0.tgz /usr/local/src/
RUN mv /usr/local/src/spark-2.2.0-bin-hadoop2.6 /usr/local/src/spark
ENV SPARK_HOME /usr/local/src/spark
ENV PATH $SPARK_HOME/bin:$PATH

RUN echo "export SPARK_HOME='/usr/local/src/spark'" >> /root/.bashrc
RUN echo "export PATH='$SPARK_HOME/bin:$PATH'" >> /root/.bashrc
