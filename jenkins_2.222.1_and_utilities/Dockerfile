FROM jenkins/jenkins:2.222.1-centos7

ENV JAVA_OPTS "-Dmail.smtp.starttls.enable=true -Dorg.apache.commons.jelly.tags.fmt.timeZone=Europe/Madrid  -Duser.timezone=Europe/Madrid"

USER root
RUN yum install -y dos2unix unzip zip scp wget sshpass

RUN mv /etc/localtime /etc/localtime.bak
RUN ln -s /usr/share/zoneinfo/Europe/Madrid /etc/localtime

RUN git config --global http.sslVerify false
RUN git config --global core.longpaths true

# volume at /var/jenkins_home -> jenkins_home

EXPOSE 8080 50000

#ENTRYPOINT ["/bin/tini -- /usr/local/bin/jenkins.sh"]
CMD /usr/local/bin/jenkins.sh

