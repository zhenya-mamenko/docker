FROM node
RUN npx create-react-app my-app
RUN cd my-app && npm install \
	chai \
	mocha \
	selenium-webdriver \
	webdriverio \
	&& npm install \
	@wdio/selenium-standalone-service \
	@wdio/cli \
	@wdio/spec-reporter --save-dev
RUN mkdir chrome && cd chrome
ADD http://chromedriver.storage.googleapis.com/74.0.3729.6/chromedriver_linux64.zip .
RUN unzip chromedriver_linux64.zip
EXPOSE 3000
CMD cd my-app && ./node_modules/.bin/wdio config && npm start
