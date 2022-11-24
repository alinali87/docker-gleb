# Part 1. Docker basics
## how to create a container
pull and run a container:  
`docker run -p 8888:8888 jupyter/scipy-notebook:85f615d5cafa`

## how to get into the container
get into the container:  
`docker exec -it 6670b433ce5d bash`

## how to copy a file into the running container
copy a file to the running container:  
`docker cp wine.csv 6670b433ce5d:/home/jovyan/wine.csv`

## how to run a container with volume
mount a volume (in fact it's not a volume - it's a bind mount):  
`docker run -v /Users/laede/git/docker-gleb:/home/jovyan -p 8888:8888 jupyter/scipy-notebook:85f615d5cafa`

## how to install a package into a container
build a new image (with xgboost installed) from Dockerfile:  
- create a Dockerfile, specify base image  
- add RUN command  
`docker build .`  
`docker run -v /Users/laede/git/docker-gleb:/home/jovyan -p 8888:8888 cd60c30a0041`  


## optional
rename tags of an existing docker image  
`docker tag cd60c30a0041 alinal55/my_jupyter:latest`

# Part 2. Docker compose
## how to add docker compose
- add docker-compose.yaml  
- specify version, service, image/build, volumes and ports  
- `docker-compose up`
- test that jupyter notebook is running and you can import xgboost

## how to install postgres
- add `db` into docker compose file
- docker-compose up

## how to connect to postgres
- go to jupyter notebook
- pip install psycopg2-binary

## how to load data to/from postgres in jupyter
- google: python dataframe to postgresql table
- ```python
  from sqlalchemy import create_engine
  engine = create_engine('postgresql://username:password@localhost:5432/mydatabase')
  df.to_sql('table_name', engine)```
- google: python dataframe from postgresql
- ```python
  df_from_pg = pd.read_sql_query('select * from wine',con=engine)```

## how to make postgres data persistent
- google: docker postgres volume
- add volumes in db section of docker-compose.yml
- add volumes section in docker-compose.yml, specify the name and don't forget a colon
