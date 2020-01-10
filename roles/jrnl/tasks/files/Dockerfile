FROM python:3.7
RUN pip install jrnl
ENV HOME /home/user
RUN set -eux; \
	useradd --create-home --home-dir "$HOME" user; \
	chown -R user:user "$HOME"
WORKDIR $HOME
USER user
CMD /bin/bash