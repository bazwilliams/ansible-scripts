FROM openjdk:11-jre

ENV url=http://jminim.com/cada/MinimServer-0.8.5.2-linux-intel.tar.gz

RUN wget -O /opt/MinimServer.tar.gz ${url} && \
		cd /opt && \
		tar xf MinimServer.tar.gz && \
		rm MinimServer.tar.gz

EXPOSE 9790 9791

ENTRYPOINT [ "/opt/minimserver/bin/startc" ]