# image name: datascience-cpu
# inspired from https://github.com/hamelsmu/Docker_Tutorial/blob/master/basic_tutorial/Dockerfile
# curl https://raw.githubusercontent.com/hamelsmu/Docker_Tutorial/master/basic_tutorial/Dockerfile > Dockerfile

# basic cpu image
## os flavor: centos
## softwares: python3, anaconda, jupyter (with nbextensions enabled)
## other python libraries: profilers (line_profiler, memory_profiler); pyarrow, fastparquet

FROM centos:latest

RUN yum -y update

RUN yum -y install wget git bzip2 python3

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh
RUN wget --quiet https://repo.continuum.io/archive/Anaconda3-5.0.0.1-Linux-x86_64.sh -O ~/anaconda.sh
RUN /bin/bash ~/anaconda.sh -b -p /opt/conda
RUN rm ~/anaconda.sh

ENV PATH /opt/conda/bin:$PATH

RUN pip install jupyter_contrib_nbextensions
RUN jupyter contrib nbextension install --user

RUN pip install line_profiler memory_profiler pyarrow
RUN conda install -c conda-forge fastparquet --yes

WORKDIR /home
