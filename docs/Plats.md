# Plats

Aquest es l'apartat per tots els endpoints que tenen a veure amb els plats de la aplicació.

## Diferents endpoints de Plats

### Insertar Plat
#### /api/plat
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet inserir un plat mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "actiu": true,
    "nom_plat": "Nombre del plato26",
    "descripcio_plat": "Descripción del plato",
    "tipus_plat": "Tipo de plato",
    "import_suplement": 10.50,
    "dies_setmana": [1, 2, 3], 
    "temps_preparacio": 45,
    "gluten": true,
    "lactosa": false,
    "imatge_plat": "nomimatge"
}
```

##### Resposta -> 200 OK
```
{
    "resposta": true
}
```

##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true o false si s'ha afegit correctament el plat.

### Llistar Plats
#### /api/llistarplats
##### GET
###### Publica / ApiKey

Aquest endpoint permet obtenir una llista de tots els plats mitjançant una petició GET amb una clau d'API vàlida.
##### Payload
```
No necesita payload
```
##### Resposta -> 200 OK
```
{
    "resposta": [
        {
            "ID_Plat": "1",
            "Actiu": "1",
            "Nom_Plat": "Sushi de salmon",
            "Descripcio_Plat": "Delicioso sushi de salmon fresco.",
            "Tipus_Plat" : "Sushi",
            "Import_Suplement": "2.50",
            "Temps_Preparacio": "30", 
            "Gluten": "1",
            "Lactosa": "1"
        }
        {
            "ID_Plat": "2",
            "Actiu": "1",
            "Nom_Plat": "Sushi de atun",
            "Descripcio_Plat": "Delicioso sushi de atun fresco.",
            "Tipus_Plat" : "Sushi",
            "Import_Suplement": "2.50",
            "Temps_Preparacio": "30", 
            "Gluten": "1",
            "Lactosa": "1"
        }
        ...
    ]
}
```
##### Lògica
Arriba una petició GET amb la clau d'API i retorna tots els plats que existeixen.

### Plat Dia
#### /api/plat
##### GET
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet obtenir tots els plats d'aquell dia mitjançant una petició GET amb un JWT vàlid.
##### Payload
```
{
    "dia": "Dissabte"
}
```

##### Resposta -> 200 OK
```
{
    "resposta": [
        {
            "ID_Plat": "1",
            "Actiu": "1",
            "Nom_Plat": "Sushi de salmon",
            "Descripcio_Plat": "Delicioso sushi de salmon fresco.",
            "Tipus_Plat" : "Sushi",
            "Import_Suplement": "2.50",
            "Temps_Preparacio": "30", 
            "Gluten": "1",
            "Lactosa": "1"
        }
        {
            "ID_Plat": "2",
            "Actiu": "1",
            "Nom_Plat": "Sushi de atun",
            "Descripcio_Plat": "Delicioso sushi de atun fresco.",
            "Tipus_Plat" : "Sushi",
            "Import_Suplement": "2.50",
            "Temps_Preparacio": "30", 
            "Gluten": "1",
            "Lactosa": "1"
        }
        ...
    ]
}
```

##### Lògica
Arriba una petició GET amb un JWT vàlid i retorna tots els plats d'aquell dia passat.

### Modificar Plat
#### /api/modificarplat
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet modificar un plat mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "actiu": true,
    "nom_plat": "Nombre del plato25",
    "descripcio_plat": "Descripción del plato",
    "tipus_plat": "Entrant",
    "import_suplement": 10.50,
    "dies_setmana": [1, 2, 3], 
    "temps_preparacio": 45,
    "gluten": true,
    "lactosa": false,
    "imatge_plat": "nomimatge"
}
```
##### Resposta -> 200 OK
```
{
    "resposta": true
}
```
##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true o false depenent de si s'ha pogut modificar o no el plat.

### Eliminar Plat
#### /api/eliminarplat
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet eliminar un plat mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "nom_plat": "Nom del plat"
}
```

##### Resposta -> 200 OK

```
{
    "resposta": true
}
```

##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true o false depenent de si s'ha pogut eliminar el plat o no.