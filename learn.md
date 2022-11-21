## how to create a container
pull and run a container:  
`docker run -p 10000:8888 jupyter/scipy-notebook:85f615d5cafa`

## how to get into the container
get into the container:  
`docker exec -it 6670b433ce5d bash`

## how to copy a file into the running container
copy a file to the running container:  
`docker cp wine.csv 6670b433ce5d:/home/jovyan/wine.csv`

## how to run a container with volume
mount a volume:  
`docker run -v /Users/laede/git/docker-gleb:/home/jovyan -p 8888:8888 jupyter/scipy-notebook:85f615d5cafa`

## how to install a package into a container
build a new image (with xgboost installed) from Dockerfile:  
- create a Dockerfile  
- add RUN command  
`docker build .`  
`docker run -v /Users/laede/git/docker-gleb:/home/jovyan -p 8888:8888 cd60c30a0041`  


## optional
rename tags of an existing docker image  
`docker tag cd60c30a0041 alinal55/my_jupyter:latest`