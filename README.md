# tjth-vpn
Simple deployment of Wireguard vpn using pre-built docker image. 

# Deployment

Deployment is simple:

* Set the number of users (PEERS) in the docker-compose file and change from the default port number (Recommended).
* `up` the docker container
```
docker-compose up -d
```
* Setup port forwarding on your gateway to forward the chosen port to your docker host (UDP)
* Execute the following command to print the QR codes for the client in the terminal:

```
sudo docker exec -it wireguard /app/show-peer [peer-number]
```

* Scan the QR code on your client

# Common commands

* To view connected clients, run the following:

```
sudo docker exec -it wireguard wg show
```

* To add a new client, update the docker-compose file to request another PEER and restart the container

```
docker-compose up -d
```