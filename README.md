# catalog

kubectl create secret generic catalog-secrets --from-literal=mongodb-password='Pass#word1'

docker network create net5tutorial
docker build -t catalog:v1 .

docker run -d --rm --name mongo -p 27017:27017 -v mongodbdata:/data/db -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1 --network=net5tutorial mongo

docker run -it --rm -p 8080:80 -e MongoDbSettings:Host=mongo -e MongoDbSettings:Password=Pass#word1 --network=net5tutorial catalog:v1
