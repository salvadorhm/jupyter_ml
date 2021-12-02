# Docker file


## Create Docker image
```bash
docker build -t salvadorhm/jupyter_ml:v0.1 .
```

## Test docker container
```bash
docker run --rm -it -p 8080:8080 salvadorhm/jupyter_ml:v0.1
```

## Start Jupyter

jupyter notebook jupyter_notebooks/