# Test del contrato
## Address disponibles
![alt text](image.png)

# Realizaremos un test siguiendo estos pasos:
## 0- estado inicial
![alt text](image-1.png)

## 1- creacion del contrato,
    - owner:    0x5B38Da6a701c568545dCfcB03FcB875f56beddC4
![alt text](image-2.png)
![alt text](image-3.png)

## 2- ofertas validas (address, $)
    - address:    0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2      100
![alt text](image-4.png)

    - address:    0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db      120
![alt text](image-5.png)

## 3- ofertas menores que maximo, las rechaza
    - address:    0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB      121
![alt text](image-6.png)

    - address:    0x617F2E2fD72FD9D5503197092aC168c91465E7f2      126
![alt text](image-7.png)

## 4- oferta mayor que maximo, la acepta
    - address:    0x17F6AD8Ef982297579C203069C1DbfFE4348c372      150
![alt text](image-8.png)

## 5- pruebas de funciones / variables / estructuras antes de finalizar la Subasta
### 5.1 bidOwner
![alt text](image-9.png)

### 5.2 getBids
![alt text](image-10.png)

### 5.3 getHighestBid
![alt text](image-11.png)

### 5.4 getWinner
![alt text](image-12.png)

### 5.5 isActive
![alt text](image-13.png)

## 6- finalizar la Subasta
### primero la ejecuto con un address incorrecto, luego con el address owner
![alt text](image-14.png)

## 7- pruebas de funciones / variables / estructuras despues de finalizar la Subasta
### 7.1 isActive muestra que no esta activa
![alt text](image-15.png)

### 7.2 getBids muestra que solo queda la oferta ganadora, el resto esta en 0 luego de devolverlas
![alt text](image-16.png)

### 7.3 getWinner
![alt text](image-17.png)

### 7.4 sendBid muestra que la Subbasta no esta activa
![alt text](image-18.png)

### 7.5 finishAuction muestra que la Subbasta no esta activa
![alt text](image-19.png)


# FIN DEL TEST 




