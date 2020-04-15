# template_project_pytorch_1_0_1

## Getting Started
```
# build container
$ cd docker
$ docker build ./ -t template_project_pytorch_1_0_1

# run container
$ sh run.sh docker

# [optional]run container which use gpu(nvidia-docker)
$ sh run.sh nvidia-docker

# start jupyter notebook
$ jupyter notebook --allow-root --port=8888 --ip=0.0.0.0 &
```

## Description
* OS version
```
$ cat /etc/issue
Ubuntu 16.04.5 LTS \n \l
```

* Python version
```
$ python -V
Python 3.6.8 :: Anaconda, Inc.
```

* PyTorch version
```
>>> torch.__version__
'1.0.1.post2'
```
