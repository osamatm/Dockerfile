FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

# python-pip is not available in ubuntu20.04. Removed python & python-pip
RUN apt-get update && \
    apt-get install -y build-essential git locales tree vim sudo less tzdata zip bash-completion npm && \
    apt-get install -y python3 python3-pip && \
    npm install -y tldr
#    apt-get clean && rm -rf /tmp/* /usr/share/doc/* /usr/share/info/* /var/tmp/*

#RUN pip install cmake --upgrade

RUN locale-gen ko_KR.UTF-8
ENV LC_ALL ko_KR.UTF-8
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

RUN useradd -ms /bin/bash -G sudo oh
RUN echo "oh:oh" | chpasswd

ARG HOMEDIR=/home/oh

USER oh
WORKDIR ${HOMEDIR}

RUN mkdir ${HOMEDIR}/workspace ${HOMEDIR}/Configuration ${HOMEDIR}/shared && \
    touch ${HOMEDIR}/.sudo_as_admin_successful

VOLUME ["${HOMEDIR}/shared"]

CMD /bin/bash
