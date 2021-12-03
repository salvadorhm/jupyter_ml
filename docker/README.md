# Docker file


## Create Docker image
```bash
docker build -t salvadorhm/jupyter_ml:CPU_v0.1 .
```

## Test docker container
```bash
docker run --rm -it -p 8080:8080 salvadorhm/jupyter_ml:CPU_v0.1

sudo docker run --rm -it --net=host --name jml_cpu -h jml_cpu salvadorhm/jupyter_ml:CPU_v0.1
```

## Start Jupyter

jupyter notebook --allow-root
