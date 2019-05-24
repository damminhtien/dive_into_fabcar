# Dive_into_fabcar
Fabric Car network: Inspire of this tutorial: https://medium.com/@kctheservant/deep-dive-into-fabcar-part-1-57c2530148a0

## Interact with cli bash

Query all car records
```bash
docker exec cli peer chaincode invoke -C mychannel -n fabcar -c '{"Args":["queryAllCars"]}'
```

Query a specific car by CarID
```bash
docker exec cli peer chaincode invoke -C mychannel -n fabcar -c '{"Args":["queryCar","CAR4"]}'
```

Add a new car
```bash
docker exec cli peer chaincode invoke -C mychannel -n fabcar -c '{"Args":["createCar", "CAR12", "Lambor", "Accord", "black", "Tien"]}'
```

Change owner of CAR4
```bash
docker exec cli peer chaincode invoke -C mychannel -n fabcar -c '{"Args":["changeCarOwner", "CAR4", "Toan"]}'
```

## Interact with api

Query all car records
```bash
curl http://localhost:8080/api/queryallcars
```

Query a specific car by CarID
```bash
curl http://localhost:8080/api/query/CAR4
```

Add a new car
```bash
curl -d '{"carid":"CAR10","make":"Honda","model":"Accord","colour":"black","owner":"Tom"}' -H "Content-Type: application/json" -X POST http://localhost:8080/api/addcar
```

Change owner of CAR4
```bash
curl -d '{"owner":"KC"}' -H "Content-Type: application/json" -X PUT http://localhost:8080/api/changeowner/CAR4
```
