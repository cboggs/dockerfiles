FROM	ubuntu:14.04

RUN	echo 'deb http://us.archive.ubuntu.com/ubuntu/ precise universe' >> /etc/apt/sources.list
RUN	apt-get -y update
RUN apt-get -y install software-properties-common
RUN	add-apt-repository ppa:chris-lea/node.js
RUN	apt-get -y update
RUN apt-get -y install nodejs git wget curl

WORKDIR /tmp
RUN git clone https://github.com/grafana/grafana

WORKDIR /tmp/grafana
RUN npm install 
RUN node_modules/grunt-cli/bin/grunt build

ADD config.js /tmp/grafana/src/config.js
ADD test.json /tmp/grafana/src/app/dashboards/test.json
ADD cboggs_demo.js /tmp/grafana/src/app/dashboards/cboggs_demo.js
ADD jdk_8.js /tmp/grafana/src/jdk_8.js
ADD experimental.js /tmp/grafana/src/experimental.js

ENTRYPOINT ["/tmp/grafana/node_modules/grunt-cli/bin/grunt"]
CMD ["server"]
