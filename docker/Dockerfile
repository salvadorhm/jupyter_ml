# Download base image ubuntu 18.04
FROM ubuntu:20.04

# LABEL about the custom image
LABEL maintainer="Salvador HM salvadorhm@gmail.com"
LABEL version="0.2"
LABEL description="This is a ubuntu:20.04 image with TensorFlow-gpu, python 3.8.10"

# Definbe ENV files
ENV requirements /home/zeo/requirements.txt

# Copy requirements file
COPY requirements.txt ${requirements}


# Install packages
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y python3
RUN apt-get install -y python3-pip
RUN pip3 install --upgrade pip
RUN apt-get install sqlite3
RUN apt-get clean

# Install python packages
RUN pip3 install -r /home/zeo/requirements.txt

#RUN useradd -ms /bin/bash zeo
#RUN useradd -d /home/zeo -g root -G sudo -m zeo
#USER zeo
WORKDIR /home/zeo
COPY jupyter_notebooks/ /home/zeo/jupyter_notebooks/ 
#RUN useradd -d /home/zeo -g root -G sudo -m zeo