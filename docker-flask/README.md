# Деплой в три команды
docker-machine create --driver generic --generic-ip-address={ip} --generic-ssh-key ~/.ssh/id_rsa test
eval $(docker-machine env test)
docker-compose up -d