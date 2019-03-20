FROM ruby
RUN gem update --system && \
	gem install rails
ONBUILD ARG DIR=./app/
ONBUILD WORKDIR /opt/app/
ONBUILD COPY $DIR .
ONBUILD RUN bundle install && \
		rake db:migrate && \
		rake db:seed
