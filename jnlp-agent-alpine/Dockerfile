ARG version=4.6-2-alpine
FROM jenkins/agent:$version

LABEL maintainer="CloudNativeLab.COM <uname.chen@gmail.com>"

ARG user=jenkins

USER root
COPY jenkins-agent /usr/local/bin/jenkins-agent
RUN chmod +x /usr/local/bin/jenkins-agent &&\
    ln -s /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-slave

USER ${user}

ENTRYPOINT ["jenkins-agent"]