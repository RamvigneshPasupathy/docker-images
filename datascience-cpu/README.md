# datascience-cpu

docker build --tag ramvignesh/datascience-cpu .

docker run -it -p {host-port}:{container-port} ramvignesh/datascience-cpu <br/>
docker run -it -p 7777:8888 ramvignesh/datascience-cpu


docker run -it -p {host-port}:{container-port} -v {host-dir}:{container-dir} ramvignesh/datascience-cpu
docker run -it -p 7777:8888 -v '~/ml-workspace-python':'/home/ml-workspace-python' ramvignesh/datascience-cpu
docker run --name ramvignesh-pyspace -it -p 7777:8888 -v 'ml-workspace-python':'/home/ml-workspace-python' ramvignesh/datascience-cpu


docker container exec -it ramvignesh-pyspace /bin/bash
docker container start ramvignesh-pyspace


jupyter notebook --ip 0.0.0.0  --no-browser --allow-root
