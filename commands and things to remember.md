sshing to remote:

- create ssh key in /.ssh
- generate ssh key 
- save ssh pub key in cloud provider 
- create ssh config: 

    Host de-zoomcamp
    HostName 34.86.236.79
    User peyton
    IdentityFile C:/Users/peyton/.ssh/gcp

- From then on simply use "ssh de-zoomcamp" 


- docker:

-- docker-compose up -d 
-- runs docker-compose yaml file in wdir 


-- docker build -- builds image from DockerFile 

docker build -t taxi_ingest:v001 from dockerfile C:\Users\peyton\repos\data-engineering-zoomcamp\week_1_basics_n_setup\2_docker_sql\Dockerfile

-- Docker run -- runs image from Docker image with args. 

This command runs the taxi_ingest:v001 image with -- as args. 

docker run -it \
  --network=pg-network \
  taxi_ingest:v001 \
    --user=root \
    --password=root \
    --host=pg-database \
    --port=5432 \
    --db=ny_taxi \
    --table_name=yellow_taxi_trips \
    --url=${URL}

volumes:

Syncs up the local storage to docker storage, allowing for stateful containers. 

     - "./ny_taxi_postgres_data:/var/lib/postgresql/data"


This argument maps the host PC's port 8080 to the container's port of 80. 
ports:
      - "8080:80"


linux stuff:

‘chmod a+x <filename>’ will basically give all the users i.e. the owner of the file, other users in the file’s group and rest others (which are not in the file's group) executable permission to the file

--- used this to provide permission to myself to execute docker-compose.exe 

wget (link) -- downloads  a file 

sftp -- copies a file from host to remote via ssh. Run this command from the host. 