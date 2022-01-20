FROM python:3.10-buster as web-base

#[DEVELOPMENT ONLY] run in shell from root location
# mkdir docker-python/base/project; rsync -av --progress ./ docker-python/base/project --exclude docker-python

# this is the python base image that contains olny git and the downloaded project
RUN apt-get update
RUN apt install git -y

WORKDIR /root

RUN mkdir flask-mongodb-example
COPY . ./flask-mongodb-example/

FROM web-base
# web-base is the Dockerfile inside ./base folder, it's splitted in 2 to speed up the multiple image build process


WORKDIR /root/flask-mongodb-example/python
RUN pip install -qr /root/flask-mongodb-example/python/requirements.txt

EXPOSE 5000
