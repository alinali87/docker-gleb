# Part 1. Docker basic
1. create a container from jupyter notebook image
2. get into the container 
3. copy a file into the running container 
4. run a container with volume 
5. install a package into a container

- optional: rename tags of an existing docker image

# Part 2. Docker compose
1. add docker-compose.yml, specify jupyter notebook service, volume, ports; `docker-compose up` must run the jupyter notebook with the same config as `docker run` in the part 1
2. add postgres database service to docker compose
3. load data to postgres from jupyter
4. load data to jupyter from postgres
5. make postgres data persistent
