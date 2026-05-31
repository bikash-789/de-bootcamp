# de-docker-bootcamp
Docker bootcamp from DataTalksClub

## To Run the DB:

`
    docker run -it \
    --network=pg-network
    -e POSTGRES_USER="root" \
    -e POSTGRES_PASSWORD="root" \
    -e POSTGRES_DB="ny_taxi" \
    -v $(pwd)/ny_taxi_postgres_data:/var/lib/postgresql \
    -p 5432:5432 \
    postgres:18
`

## To Run the docker container:

`
    docker run -it --rm \
    --network=pg-network \
    taxi_ingest:v001 \
    --pg-user=root \
    --pg-password=root \
    --pg-host=pgdatabase \
    --pg-port=5432 \
    --pg-db=ny_taxi \
    --target-table=yellow_taxi_trips_2021_1 \
    --chunk-size=100000
`