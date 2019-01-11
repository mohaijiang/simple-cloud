FROM openjdk:8u181-jre-slim-stretch
RUN groupadd app && useradd -g app -d /home/app -s /bin/sh -m app
USER app
ARG PROJECT_NAME
ARG JAR_FILE
WORKDIR /home/app/${PROJECT_NAME}
COPY target/${JAR_FILE} /home/app/${PROJECT_NAME}
COPY entrypoint.sh /home/app/${PROJECT_NAME}
ENV JAR_FILE=${JAR_FILE}
EXPOSE 8080
ENTRYPOINT ["bash", "./entrypoint.sh"]