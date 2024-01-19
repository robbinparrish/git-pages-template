FROM debian:12.4

ENV DEBIAN_FRONTEND=noninteractive

# Perform an update.
RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get clean all

# Install common utilities and tools.
RUN apt-get update && \
	apt-get install -y --no-install-recommends --no-install-suggests \
	bash curl wget tar zip bzip2 xz-utils \
	unzip ca-certificates git vim \
	default-jdk python3-pip python3-dev \
	graphviz fontconfig && \
	apt-get clean all

# Install poetry.
RUN pip install --break-system-packages poetry==1.7.1

# Install Plantuml.
ENV PLANTUML_VERSION="1.2023.13"
ENV PLANTUML_JAR="/opt/plantuml/plantuml.jar"
RUN mkdir -p /opt/plantuml && \
	wget https://github.com/plantuml/plantuml/releases/download/v${PLANTUML_VERSION}/plantuml-gplv2-${PLANTUML_VERSION}.jar -O /opt/plantuml/plantuml.jar && \
	echo '#!/bin/sh\njava -jar /opt/plantuml/plantuml.jar "$@"' | tee /usr/bin/plantuml && \
	chmod 755 /usr/bin/plantuml

# Create default user.
ENV USER_ID=1000
ENV USER_NAME=devuser
RUN addgroup --gid ${USER_ID} ${USER_NAME} && \
	adduser --disabled-password --gecos "" \
	    --uid ${USER_ID} --gid ${USER_ID} ${USER_NAME}

# Set default user.
ENV HOME /home/devuser
USER devuser

CMD /bin/bash
