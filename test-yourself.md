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
3. start jupyter, read data from wine.csv into pandas DataFrame --> df
4. load data from df to postgres wine table
5. read data from postgres wine table to pandas DataFrame --> df_pg
6. remove the container, run a new container, and see that postgres has no wine table
7. make postgres data persistent
8. remove the container, run a new container, and see that postgres has wine table
