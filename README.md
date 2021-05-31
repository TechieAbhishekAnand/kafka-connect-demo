# kafka-connect-demo

Step by step commands run in powershell on windows only:

1. setx GITHUB_REPO_MASTER=https://raw.githubusercontent.com/streamthoughts/kafka-connect-file-pulse/master/
2. curl https://raw.githubusercontent.com/streamthoughts/kafka-connect-file-pulse/master/docker-compose.yml -o docker-compose.yml
3. docker-compose up -d
4. docker-compose logs "connect-file-pulse"
5. curl -sX GET http://localhost:8083/connector-plugins
6. curl http://localhost:8083/connector-plugins - and from above result look for FilePulseSourceConnector
7. curl https://raw.githubusercontent.com/streamthoughts/kafka-connect-file-pulse/master/examples/connect-file-pulse-quickstart-log4j.json -o connect-file-pulse-quickstart-log4j.json
8. curl.exe -sX PUT http://localhost:8083/connectors/connect-file-pulse-quickstart-log4j/config -d @connect-file-pulse-quickstart-log4j.json --header "Content-Type: application/json" - after this I am getting this error.

{"error_code":400,"message":"Connector configuration is invalid and contains the following 1 error(s):\nMissing required configuration \"internal.kafka.reporter.bootstrap.servers\" which has no default value.\nYou can also find the above list of errors at the endpoint `/connector-plugins/{connectorType}/config/validate`"}

I will update once I get solution for this.

Thanks
