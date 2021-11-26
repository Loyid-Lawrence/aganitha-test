1. Get .pem of my ec2 instance from loyid(me :P)
2. ssh -L 8888:localhost:8888 -i "test1.pem" ubuntu@ec2-15-206-66-208.ap-south-1.compute.amazonaws.com
3. go to localhost:8888
4. Enter Token number of jupyter notebook running on 8888:
	1cf60a9b258729295c178015f8d9da4b1362358f7622f6fd



instructions to create table:
1. https://www.compose.com/articles/getting-started-with-compose-postgresql-and-jupyter-notebooks/


To go into the docker postgres:
1. docker exec -it aganitha_postgres bash
2. i. psql -U docker
   ii. create database compose
   iii. psql "host=localhost port=5432 dbname=compose user=docker"  
   iv. CREATE TABLE passengers (  
    id SERIAL NOT NULL PRIMARY KEY, 
    survived INT,
    pclass INT,
    name VARCHAR(255),
    sex TEXT,
    age FLOAT8,
    siblings_spouses INT,
    parents_children INT,
    fare FLOAT8
);
   v. \copy passengers (survived, pclass, name, sex, age, siblings_spouses, parents_children, fare) from '/titanic.csv' CSV HEADER; 


if the docker is down 
1. cd aganitha
2. docker-compose up -d
