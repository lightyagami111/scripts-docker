### Run postgres server
https://elanderson.net/2018/02/setup-postgresql-on-windows-with-docker/
> The problem with this approach is if you ever need to rebuild the container for some reason, like a new version of Postgres is released, your data will be lost

`docker run -p 5432:5432 --name PostgresqlC -e POSTGRES_PASSWORD=I3VE6s5upFBvN -d postgres`

remote login postgres : I3VE6s5upFBvN

### Run postgres admin

https://hub.docker.com/r/dpage/pgadmin4/

`docker pull dpage/pgadmin4`

https://www.bojankomazec.com/2020/02/running-pgadmin-in-docker-container.html

`docker run -p 5051:5051 -d -e "PGADMIN_DEFAULT_EMAIL=PostgresqlC@postgres.com" -e "PGADMIN_DEFAULT_PASSWORD=I3VE6s5upFBvN" -e "PGADMIN_LISTEN_PORT=5051" --rm --name pgadmin --network bridge dpage/pgadmin4`


### Connect server to pgadmin
1. See Container details for PostgresqlC IP address
2. Open <IP address of pgadmin>:5051
3. Connect to <IP address of PostgresqlC> with postgres & POSTGRES_PASSWORD
