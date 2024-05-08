# Mail

Aquest es l'apartat per tots els endpoints que tenen a veure amb el mailing de la aplicació.

## Diferents endpoints de Mail

### Mail a l’usuari
#### /api/mail
##### POST
###### Privada: es necessita jwt i/o estar loguejat

Aquest endpoint permet enviar un correu electrònic a l'usuari mitjançant una petició POST amb un JWT vàlid.
##### Payload
```
{
    "mail": "a2207803@institutmontilivi.cat",
    "msg": "<body style='background-color:#000;color:#fff;font-family:Arial,sans-serif;margin:10px;padding:10px;'><div style='width:80%;margin:50px auto;background-color:#333;border-radius:20px;padding:20px;box-shadow:0px 0px 20px rgba(255, 255, 255, 0.2);'><h1 style='color:#ff6f61;text-align:center;'>¡Merci per confiar en nosaltres!</h1><p style='color:#fff;'>Merci per haber comprat al nostre restaurant</p><p style='color:#fff;'>Per dubtes o preguntes, contacta amb nosaltres a grabandgoshushi@gmail.com</p><p style='font-size:36px;text-transform:uppercase;text-align:center;color: #ff6f61;animation:rainbow-text 5s infinite;'>¡Disfruta del teu menjar!</p></div></body><style>@keyframes rainbow-text {0% {color:#ff6f61;}20% {color:#76d275;}40% {color:#ffcb77;}60% {color:#33cccc;}80% {color:#ff5e62;}100% {color:#aa80ff;}}</style>"
}
```

##### Resposta -> 200 OK
```
{
    "resposta": true
}
```
##### Lògica
Arriba una petició POST amb un JWT vàlid i retorna true o false en cas d'haver enviat correctament el correu electrònic a l'usuari.