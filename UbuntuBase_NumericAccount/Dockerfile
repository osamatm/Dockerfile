FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

# python-pip is not available in ubuntu20.04. Removed python & python-pip
RUN apt-get update && \
    apt-get install -y build-essential git locales tree vim sudo less tzdata zip bash-completion tldr && \
    apt-get install -y python3 python3-pip
#    apt-get clean && rm -rf /tmp/* /usr/share/doc/* /usr/share/info/* /var/tmp/*

#RUN pip install cmake --upgrade

RUN locale-gen en_US.UTF-8
ENV LC_ALL en_US.UTF-8
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

RUN useradd -ms /bin/bash -G sudo 1234567
RUN echo "1234567:1234567" | chpasswd

# RUN useradd -ms /bin/bash 1234567 && usermod -aG sudo 1234567
# RUN echo "1234567:1234567" | chpasswd

ARG HOMEDIR=/home/1234567

# Need to consider how to get uid for account name
# ARG MYUID
# RUN export MYUID="$(id -u 1234567)"
# RUN echo ${MYUID}
# RUN ["id", "-u", "1234567"]
# RUN ${MYUID}="$(id -u 1234567)"

# USER ${MYUID}
USER 1000
WORKDIR ${HOMEDIR}

RUN mkdir ${HOMEDIR}/workspace ${HOMEDIR}/Configuration ${HOMEDIR}/shared && \
    touch ${HOMEDIR}/.sudo_as_admin_successful

VOLUME ["${HOMEDIR}/shared"]

CMD /bin/bash
