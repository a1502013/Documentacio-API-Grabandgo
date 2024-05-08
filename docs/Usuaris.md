# Usuaris

Aquest es l'apartat per tots els endpoints que tenen a veure amb els usuaris de la aplicació.

## Diferents endpoints d'Usuaris

### Signup
#### /api/usuaris/signup
##### POST
###### Public / ApiKey

Aquest endpoint retorna totes les dades se l'usuari demanat:
##### Payload
```
{
    "usuari": "Imad22",
    "mail": "Imad60@mail.com",
    "password": "Imad1234*"
}
```
##### Resposta
```
{
    "resposta": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiZ3JhYmFuZGdvc2h1c2hpQGdtYWlsLmNvbSIsInVzZXJuYW1lIjoiYWRtaW4iLCJleHAiOm51bGx9.lWqU3z-EMe5zhehoPertYdiozqIp5504qNaQo9sQacw"
}
```
##### Descripció

Arriba una petició POST amb la api key i retorna un jwt si el signup és correcte amb el que poder fer altres peticions.

### Login
#### /api/usuaris/login
##### POST
###### Public / ApiKey

Aquest endpoint permet a l'usuari iniciar sessió i obtenir un JWT per a les peticions futures.
##### Payload
```
{
    "usuari": "Imad22",
    "password": "Imad1234*"
}
```
##### Resposta
```
{
    "resposta": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiZ3JhYmFuZGdvc2h1c2hpQGdtYWlsLmNvbSIsInVzZXJuYW1lIjoiYWRtaW4iLCJleHAiOm51bGx9.lWqU3z-EMe5zhehoPertYdiozqIp5504qNaQo9sQacw"
}
```
##### Descripció

Arriba una petició POST amb la api key i retorna un JWT si el login és correcte, permetent fer altres peticions amb aquest token.


#### Dades usuari

### Dades usuari
#### /api/usuaris/id
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir les dades de l'usuari mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
{
    "id": "2"
}
```
##### Resposta -> 200 OK
```
{
    "ID_Usuari": "2",
    "Mail": "user@mail.com",
    "Username": "User"
}
```

##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna les dades de l'usuari en qüestió. Si l'usuari no existeix, retorna el missatge adequat.

### Crear comanda
#### /api/comanda/crearcomanda
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet crear una comanda mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "Numero_Comanda": 1,
    "ID_Usuari": "1",
    "ID_Plat": "2",
    "Data_Comanda": "2024-02-11",
    "Estat": "On_Hold",
    "Hora_Inici_Preparacio": "12:00:00",
    "Temps_Preparacio": "30"
}
```

##### Resposta -> 200 OK
```
{
    "resposta": true
}
```
##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true o false depenent de si s'ha pogut crear la comanda o no.