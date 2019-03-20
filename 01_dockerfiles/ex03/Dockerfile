FROM ubuntu
RUN apt-get update -y && apt-get upgrade -y \
	&& apt-get install -y \
	ca-certificates \
	openssh-server \
	postfix \
	wget
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh \
	&& chmod 777 ./script.deb.sh \
	&& ./script.deb.sh
RUN apt-get install -y gitlab-ce \
	&& apt update \
	&& apt install -y tzdata \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
EXPOSE 22 80 443
RUN (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure

CMD (/opt/gitlab/embedded/bin/runsvdir-start &) && tail -f /dev/null
