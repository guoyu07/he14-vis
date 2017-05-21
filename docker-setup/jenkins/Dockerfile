# inherit from official jenkins image with specific version
FROM jenkins:2.46.2

# set root for installing tools
USER root

# install packages
RUN apt-get -y update \
    && apt-get install -y sudo make libtool \
    && rm -rf /var/lib/apt/lists/*

# add jenkins to sudoers
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

# switch to regular jenkins user - good practice
USER jenkins
