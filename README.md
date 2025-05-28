## Slide 1 : GameKittens API
### Que fa la api?
L'API actua com a intermediari entre l'aplicació i la base de dades, ens ofereix una capa addicional d’abstracció, on l'aplicació fa peticions a l'API i aquesta les processa, (pausa lista) accedeix a la base de dades i retorna l’informacio solicitada.

Aixo ens ofereix una millor seguretat, organitzacio i escabilitat, ya que la aplicacio no accedeix directament a la base de dades.

### Com ho fa?
Per a aquest projecte hem creat l'API en l’entorn .NET, utilitzant una base de dades SQL i funcionalitats pròpies del .NET, com  l’AppDbContext, per comunicar-nos amb la base de dades.

Hem desplegat l'API i la base de dades SQL utilitzant els serveis d'Azure.



## Slide 2 : Base de dades
A la base de dades tenim dues entitats: els empleats, com a ApplicationUser, i les tasques sostenibles, com a STask.

La relació entre ells és d’un a molts: un empleat pot tenir diverses tasques, però una tasca només pertany a un empleat.

Cal afegir que tenim una taula auxiliar per gestionar les votacions de les tasques dins de l’aplicació, on hi ha l’ID de la votació, l’ID de l’usuari que està votant i l’ID de la tasca votada.



## Slide 3 : Estructura de l’API
Aquests són els punts més importants que formen la nostra API

### AppDbContext
És la classe encarregada de la connexió amb la base de dades. Defineix les entitats existents i com es relacionen.

A més, ens permet fer operacions amb la base de dades a través de l’Entity Framework.

### Models
Són classes que representen les entitats de la base de dades.

### DTOs
Són classes POCO que s'utilitzen per transferir dades entre les capes de client i servidor.

És recomanable utilitzar-les, perquè controles millor la informació que envies o reps.

### Controllers
Són classes que gestionen les peticions HTTP. S'encarreguen de rebre la sol·licitud, processar-la i retornar una resposta.



## Slide 4: Endpoints
Un endpoint és un punt d’accés a la teva API que permet a una aplicació interactuar amb el servidor mitjançant una URL i un mètode HTTP.

Els endpoints els podem trobar als controladors de cada taula.

### Endpoints generals a la nostra API
De manera general, tots els controladors tindran aquests endpoints:
- **HttpGet**: Per obtenir totes les dades d'una taula.
- **HttpGet {id}**: Per obtenir una dada en concret d'una taula.
- **HttpPost**: Per afegir dades a una taula.
- **HttpDelete**: Per esborrar dades d'una taula.
- **HttpPut**: Per actualitzar dades d'una taula.

### Endpoints especials
A més, per facilitar algunes funcions de l’aplicació, hem creat alguns endpoints dedicats a tasques específiques:
- **HttpPost/Like**: Per afegir un vot positiu a una tasca.
- **HttpPost/Dislike**: Per afegir un vot negatiu a una tasca.
- **HttpPost/GivePoints**: Per enviar alguns punts teus a un altre usuari.




## Slide 5 : Rols
Ara us preguntareu... Llavors, tothom podrà accedir a la base de dades? Doncs no.

Perquè tenim rols. Aquests rols es poden assignar als usuaris i permeten definir quins permisos té cadascú.

A continuació, podeu veure una taula amb el controlador d'usuaris i els permisos assignats a cada rol.



## Extra Slide 1 : Presentacio
Som la Laura, l’Unai i jo, en Miquel, i venim de GameKittens per presentar-vos el nostre projecte: EcoPets.

## Extra Slide 2 : Fitxa de l'Empresa


## Extra Slide 3 : Complicacions (last)
L’aplicació es troba en fase beta. Què vol dir això?  
Que està en fase de proves i pot contenir funcions no implementades o amb errors.

En el nostre cas, la funció de mascota virtual no està implementada.  
Hem decidit no desenvolupar-la perquè volíem centrar-nos en la funció principal de l’aplicació: el sistema de tasques i punts.

En futures actualitzacions, i amb el feedback del client, podrem implementar-la com a funcionalitat extra.
