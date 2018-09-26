# Jupyter/pyspark-notebook

This dockerfile contains custom configurations over the [base notebook](https://github.com/jupyter/docker-stacks/tree/master/pyspark-notebook) with more up-to-date packages and other libs like xgboost, lightgbm, catboost, scikit-optimize, etc.

## Instalation

To build this image, you can do via the command line:

```bash
$ docker image build -t jupyter_spark_custom .
```

## Run the jupyter server

To start the jupyter notebook server using docker you can do it with the following command:

```bash
$ docker run --rm -p 8888:8888 -v $(PWD)/notebooks:/home/jovyan/work --name jupyter_pyspark jupyter_spark_custom
```

where `$(PWD)/notebooks` would be a folder where you would store all your notebooks. To store your notebooks in a different path just change this input.

If you want to start a jupyterlab instead, you can do it with the following command (assuming you are using the `notebooks/` path as an example):

```bash
$ docker run --rm -p 8888:8888 -v $(PWD)/notebooks:/home/jovyan/work --name jupyter_pyspark jupyter_spark_custom start.sh jupyter lab
```