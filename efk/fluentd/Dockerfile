# fluentd/Dockerfile

FROM fluent/fluentd:v1.14.3-1.1
USER root
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "5.1.4"]
USER fluent