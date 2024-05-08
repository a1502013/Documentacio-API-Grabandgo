# Settings

Aquest es l'apartat per tots els endpoints que tenen a veure amb els settings de la aplicació.

## Diferents endpoints de Settings

### Login intranet
#### /api/settings/intranet
##### POST
###### Public / ApiKey

Aquest endpoint permet a l'administrador iniciar sessió a la intranet i obtenir un JWT per a les peticions futures.
##### Payload
```
{
    "password": "admin1234*"
}
```
##### Resposta
```
{
    "resposta": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiYWRtaW4iLCJ1c2VybmFtZSI6ImFkbWluIiwiZXhwIjpudWxsfQ.ZO4D0nJ4_ZWEF4VE9ikYzKdtK2imxvPR7lqLwGZzQ48"
}
```
##### Descripció

Arriba una petició POST amb la api key i retorna un JWT si el login de l'administrador és correcte, permetent fer altres peticions amb aquest token.

### Preu Menu
#### /api/settings/preu_menu
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir el preu definit del menú mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
No necesita payload
```
##### Resposta -> 200 OK
```
{
    "resposta": "23"
}
```
##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna el valor definit com a preu del menú. Si la API no pot accedir a la base de dades, retorna un valor predeterminat de 25.