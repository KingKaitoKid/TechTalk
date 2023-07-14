# Descrizione
Il sito sarà fruibile da chiunque, anche da chi non è registrato.
Nella home verranno mostrati i post recenti, rilevanti basati per categoria, ci saranno anche gli utenti più attivi come publisher e utenti che commantano di più.
In aggiunta ci saranno tutti i tool per fare le pubblicazioni, registrarsi, fare il login, amministrare, modificare il profilo, interagire con i vari post (modificarlo, cancellarlo, commentare, reagire, ...)


---


# API
Per creare tutto verranno create delle API dedicate che avranno compiti specifici in base al contesto.
1. [Registrazione](#registrazione)
2. [Login](#login)
3. [Creazione post](#crea-post)

## Response standard
Le response, salvo specifici casi indicati puntualmente, saranno tutte le medesime per tutte le API e saranno composte in questo modo:
|Nome|Tipo|Mandatory|Note|
|----|----|---------|----|
|meta|Object|si|-|
|meta.status|boolean|si|-|
|meta.code|integer|si|-|
|meta.message|string|no|Obbligatorio solo se meta.status != True e/o meta.code != 200|
|data|Object|no|-|

`meta` indica informazioni della comunicazione e svolgimento azione, in caso di tutto ok `status` sarà a `true` mentre `code` deve essere `200` (HTTP Status Code), `message` va compilato in caso di errore o con `status` a `false` oppure un code diverso da `200`.
La sezione `data` è un oggetto che conterrà tutte le informazioni di ritorno se sono attese, se non è atteso un ritorno il campo `data` può essere anche omesso in quanto **facoltativo**.


## Registrazione

### Request
|Nome|Tipo|Mandatory|Note|
|----|----|---------|----|
|nome|String|si|max 100 caratteri|
|cognome|String|si|max 100 caratteri|
|dataNascita|Date|si|Nel formato yyyy-mm-dd|
|sesso|String|si|solo 2 opzioni M o F|
|telefono|String|no|Con o senza prefisso|
|email|String|si|max 255 caratteri|
|password|String|si|deve essere un sha-256|

### Response
La response è quella [Standard](#response-standard)


## Login

### Request
|Nome|Tipo|Mandatory|Note|
|----|----|---------|----|
|email|String|si|max 100 caratteri|
|password|String|si|max 100 caratteri|
|dataNascita|Date|si|Nel formato yyyy-mm-dd|
|sesso|String|si|solo 2 opzioni M o F|
|telefono|String|no|Con o senza prefisso|
|email|String|si|max 255 caratteri|

### Response
La response è quella [Standard](#response-standard)


## Crea post

### Request
|Nome|Tipo|Mandatory|Note|
|----|----|---------|----|
|titolo|String|si|Titolo del post|
|microCategoria|String|no|La categoria di appartenenza se possibile (e.g. Chimica)|
|categoria|String|si|La macrocategoria di appartenenza (e.g. Anime, Scienza)|
|descrizioneBreve|String|si|max 100 caratteri, anteprima nel link|
|descrizioneLunga|String|si|Descrizione visulizzata come anteprima del post sul sito|
|autore|String|si|Chi ha scritto il post|
|tags|String|no|Tag per rintracciare, divisi da virgole|
|visibilita|String|si|Pubblico, privato, limitato|

### Response
La response è quella [Standard](#response-standard)