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

WORKDIR /opt
RUN git clone https://github.com/merces/aleph.git
RUN pip-upgrade --skip-virtualenv-check install /opt/aleph/requirements.txt -p all
RUN cp /opt/aleph/aleph/settings.py.orig /opt/aleph/aleph/settings.py
RUN printf "\nSECRETE_KEY='`openssl rand -base64 32`'" >> /opt/aleph/aleph/settings.py #Add a secret key
RUN /opt/aleph/bin/db_create.py

EXPOSE 5000
