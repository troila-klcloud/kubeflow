FROM docker.io/kubeflownotebookswg/codeserver:v1.9.2

USER root

# s6 - copy scripts
#COPY s6/ /etc

#RUN chown ${NB_USER}:${NB_GID} /etc/services.d/ -R && chmod 755 /etc/services.d/ -R

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt install -y \
       openssh-server sssd libnss-sss libpam-sss ldap-utils \
    && systemctl disable ssh.service \
    && apt clean \
    && mkdir -p /run/sshd \

USER $NB_UID

EXPOSE 22

