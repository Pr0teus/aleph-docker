FROM debian

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y python-pyrex
RUN apt-get install -y libffi-dev
RUN apt-get install -y libfuzzy-dev
RUN apt-get install -y python-dateutil
RUN apt-get install -y libsqlite3-dev
RUN apt-get install -y python-pip
RUN apt-get install -y git vim wget
RUN pip install pip --upgrade
RUN pip install pip-upgrader

RUN mkdir -p /opt/data/samples
RUN mkdir -p /opt/data/temp
RUN mkdir -p /opt/data/unprocessed_samples

VOLUME ["/opt/data", "/opt/aleph"]
WORKDIR /opt
#RUN pip_upgrade --skip-virtualenv-check install -r /opt/aleph/requirements.txt
RUN pip install -r aleph/requirements.txt
RUN echo "SECRETE_KEY='`openssl rand -base64 32`'" > aleph/settings.py #Add a secret key
RUN bin/db_create.py

EXPOSE 5000
