FROM ubuntu:jammy

ARG ssh_prv_key
ARG ssh_pub_key


WORKDIR /ansible

COPY ./ssh_keys/ .
COPY ./ansible_vol/ .

RUN apt update
RUN apt install software-properties-common -y
RUN add-apt-repository -y --update ppa:ansible/ansible
RUN apt install tree -y
RUN apt install net-tools
RUN apt install ansible -y
RUN apt install awscli -y

RUN mkdir -p /root/.ssh && \
        chmod 0700 /root/.ssh

RUN echo "$ssh_prv_key" > /root/.ssh/id_rsa && \
    echo "$ssh_pub_key" > /root/.ssh/id_rsa.pub && \
    chmod 0600 /root/.ssh/id_rsa && \
    chmod 0600 /root/.ssh/id_rsa.pub 




