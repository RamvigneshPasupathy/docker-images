# datascience-cpu

docker build --tag ramvignesh/datascience-cpu .

docker run -it -p <host-port>:<container-port> ramvignesh/datascience-cpu <br/>
docker run -it -p 7777:8888 ramvignesh/datascience-cpu

jupyter notebook --ip 0.0.0.0  --no-browser --allow-root