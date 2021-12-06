# Jupyter Notebook for ML


## Notebook for Machine Learning

This images config a ubuntu:20.04 container, with Numpy, Pandas, Matplot, Sklearn, Seaborn, Tensorflow and Jupyter Notebooks.
## OS
```
ubuntu:20.04
```

## Libraries versions

```
numpy==1.18.5
matplot==0.1.9
matplotlib==3.5.0
mysql-connector-python==8.0.17
pandas==1.3.4
tensorflow==2.2.0
sklearn==0.0
scikit-learn==1.0.1
web.py==0.62
SQLAlchemy==1.4.27
python-telegram-bot==5.3.0
jupyter==1.0.0
jupyter-core==4.6.3
seaborn==0.11.2
```

## Docker pull

```bash
docker pull salvadorhm/jupyter_ml:CPU_v0.1
```

## Docker container

```
sudo docker run --rm -it --net=host -v local_path:/home/zeo/volume --name jml_cpu -h jml_cpu salvadorhm/jupyter_ml:v0.1
```

## Jupyter Notebook run

```bash
jupyter notebook --allow-root
```

## Dockerfile

```
# Download base image ubuntu 18.04
FROM ubuntu:20.04

# LABEL about the custom image
LABEL maintainer="Salvador HM salvadorhm@gmail.com"
LABEL version="0.1"
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

WORKDIR /home/zeo
```

## requirements.txt
```
numpy==1.18.5
matplot==0.1.9
matplotlib==3.5.0
mysql-connector-python==8.0.17
pandas==1.3.4
tensorflow==2.2.0
sklearn==0.0
scikit-learn==1.0.1
web.py==0.62
SQLAlchemy==1.4.27
python-telegram-bot==5.3.0
jupyter==1.0.0
jupyter-core==4.6.3
seaborn==0.11.2
```