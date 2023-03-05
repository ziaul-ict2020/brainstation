brs1
install Docker
sudo apt install docker-ce docker-ce-cli containerd.io -y

docker version

Laravel project
composer create-project laravel/laravel app1

build
docker build -t app1 .

docker tag app1 manobrata/brsimage1:app1

docker push manobrata/brsimage1:app1

For app2
docker tag app2 manobrata/brsimage1:app2

docker push manobrata/brsimage1:app2

Create jenkins container with docker compose file
docker-compose up -d

docker-compose ps

for web login password
docker logs jenkins | less
