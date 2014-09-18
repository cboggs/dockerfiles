Run container:
docker run -d -P influxdb
-or-
docker run -d -p 1234:8083 -p 5678:8086

Admin interface is exposed on port 8083 in the container. API port is 8086.

To run data generator script, just swap out the host name in the curl at the top of the script to point to the appropriate hostname:port and execute.

For added fun, pair this up with github.com/RallySoftware/docker-grafana to see swanky graphs!
