Run container:
docker run -d -P grafana
-or-
docker run -d -p 1234:5601 grafana

Grunt server runs on port 5601 in the container.

For added fun, link up with github.com/cboggs/dockerfiles/influxdb!
