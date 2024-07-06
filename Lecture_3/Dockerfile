# Maven Build Docker File
FROM jenkins/slave:3046.v38db_38a_b_7a_86-2-alpine
MAINTAINER "Ansh Shrivas <anshshrivas26@gmail.com>"


# Installing Maven
RUN microdnf install maven

# Install git and ssh, and sudo
RUN microdnf install git sudo openssh-server passwd

# Create user jenkins
RUN useradd -ms /bin/bash jenkins
RUN echo "jenkins" | passwd --stdin jenkins
RUN echo "root" | passwd --stdin root
RUN usermod -aG wheel jenkins

RUN ssh-keygen -A

# WORKDIR
WORKDIR /home/jenkins

# Expose ssh port
EXPOSE 22

# Start ssh service
CMD ["/usr/sbin/sshd", "-D"]


