FROM ubuntu

RUN apt-get update && apt-get install -y firefox

#TODO: Replace  with your user id / group id
RUN export uid=93871 gid=201
RUN mkdir -p /home/developer
RUN mkdir -p /etc/sudoers.d
RUN echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd
RUN echo "developer:x:${uid}:" >> /etc/group
RUN echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer
RUN chmod 0440 /etc/sudoers.d/developer
RUN chown ${uid}:${gid} -R /home/developer

USER developer
ENV HOME /home/developer
CMD /usr/bin/firefox
