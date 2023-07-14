# Generale
L'obiettivo è creare un sito web che permetta di:
- Creare nuovi post
- Vedere post
- Modificare post
- Creare un nuovo utente
- Visualizzare il proprio profilo
- Accedere al pannello degli amministratori
    - Modificare contenuto di un post (anche se non è suo)
    - Modificare visibilità di un post (nasconderlo al pubblico, autore incluso)
    - Modificare permessi di un utente a solo lettore o pubblicatore
    - Modificare le categorie dei post


# Tecnologie
Per realizzare l'intero progetto usare:
- MySQL
- PHP 8
- Python 3.10
- React.js

# POST
I post sono il contenuto dell'intero progetto, possono scriverli solo chi ha il ruolo di publisher o admin.
I post hanno le seguenti caratteristiche:
- Macro Categoria
- Categoria
- Titolo
- Contenuto
- Tag
- Descrizione breve e lunga
- Autore
- Commenti
- Mappa riassuntiva (facoltativa)
- Visibilità (pubblica, ristretto ovvero registrati, privato ovvero solo autore può vederlo)

# Utenti
Gli utenti sono gli scrittori o fruitori dei contenuti.
In base alla visibilità del post è necessario essere registrati o meno.
Gli utenti hanno le seguenti caratteristiche:
- Nome
- Cognome
- Email
- Telefono (facoltativo)
- Telegram Username (facoltativo)
- Ruolo