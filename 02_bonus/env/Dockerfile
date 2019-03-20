FROM debian
RUN apt-get update -y && apt-get upgrade -y \
	&& apt-get install -y \
	curl \
	emacs \
	gcc \
	git \
	zsh
ADD https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh .
USER root
RUN chmod 777 install.sh && ./install.sh && rm install.sh \
	&& cd ~ && echo "alias gccc='gcc -Wall -Wextra -Werror \$*'" >> .zshrc \
	&& mkdir /projects
CMD cd /projects && zsh
