# Comandes

Aquest es l'apartat per tots els endpoints que tenen a veure amb els comandes de la aplicació.

## Diferents endpoints de Comandes

### Numero Comandes Usuari
#### /api/comanda/ncomandes
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir el nombre de comandes associades a l'usuari mitjançant una petició GET amb un JWT vàlid i el correu electrònic de l'usuari.
##### Payload
```
{
    "mail": "clientquenoexisteix@mail.com"
}
```
##### Resposta -> 200 OK
```
{
    "resposta": "4"
}
```

##### Lògica
Arriba una petició GET amb un JWT vàlid i el correu electrònic de l'usuari, i retorna la quantitat de comandes que pertanyen a aquest usuari.

### Modificar Estat Comanda
#### /api/comanda/modificarestatcomanda
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet modificar l'estat d'una comanda mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "id_comanda": "2",
    "estat":"Ready"
}
```
##### Resposta -> 200 OK
```
{
    "resposta": true
}
```
##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true i 200 en cas d'haver modificat correctament l'estat de la comanda i false i 401 en cas de no haver-se fet la modificació.

### Llistar comandes usuari
#### /api/comanda/llistarcomandesusuari
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir la llista de comandes de l'usuari mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
{
    "mail": "clientquenoexisteix@mail.com"
}
```
##### Resposta -> 200 OK
```
{
    "resposta": [
        {
            "ID_Comanda": "1",
            "ID_Usuari": "1",
            "ID_Plat": "1",
            "Data_Comanda": "2000-01-01",
            "Estat" : "Ready",
            "Hora_Inici_Preparacio": "12:00:00",
            "Hora_Final_Preparacio": "12:30:00"
        }
        {
            "ID_Comanda": "2",
            "ID_Usuari": "2",
            "ID_Plat": "2",
            "Data_Comanda": "2000-01-01",
            "Estat" : "Ready",
            "Hora_Inici_Preparacio": "12:00:00",
            "Hora_Final_Preparacio": "12:30:00"
        }
        ...
    ]
}
```
##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna la llista de comandes de l'usuari o un missatge d'error indicant paràmetres incorrectes.

### Llistar comandes
#### /api/comanda/llistarcomandes
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir la llista de totes les comandes mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
No necesita payload
```
##### Resposta -> 200 OK
```
{
    "resposta": [
        {
            "ID_Comanda": "1",
            "ID_Usuari": "1",
            "ID_Plat": "1",
            "Data_Comanda": "2000-01-01",
            "Estat" : "Ready",
            "Hora_Inici_Preparacio": "12:00:00",
            "Hora_Final_Preparacio": "12:30:00"
        }
        {
            "ID_Comanda": "2",
            "ID_Usuari": "2",
            "ID_Plat": "2",
            "Data_Comanda": "2000-01-01",
            "Estat" : "Ready",
            "Hora_Inici_Preparacio": "12:00:00",
            "Hora_Final_Preparacio": "12:30:00"
        }
        ...
    ]
}
```
##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna la llista de totes les comandes disponibles.

### Numero Ultima Comanda
#### /api/comanda/ultimacomanda
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir el número de l'última comanda mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
No necesita payload
```
##### Resposta -> 200 OK
```
{
    "resposta": "4"
}
```

##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna l'últim número de comanda.