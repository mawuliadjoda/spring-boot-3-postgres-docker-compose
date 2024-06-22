./mvnw package -DskipTests

./mvnw clean install -DskipTests

./mvnw spring-boot:build-image -DskipTests

docker build -t spring-boot-3-postgres-docker-compose .

docker compose up

docker compose down


# linux
docker rmi -f $(docker images -aq)
# Windows - Powershell
# docker images -a -q | % { docker image rm $_ -f }
# cmd
for /F %i in ('docker images -a -q') do docker rmi -f %i