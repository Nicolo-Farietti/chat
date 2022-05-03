FUNZIONAMENTO CHAT:

step1(login.php) --> Login, Qui abbiamo i dettagli dell'utente autenticati come nome utente e password. 
          Se entrambi i dettagli sono corretti, può accedere a questo sistema di chat online. 
          Altrimenti otterrà un errore di informazioni errate sulla pagina web. Supponiamo che l'utente abbia inserito i dettagli corretti,
          quindi può accedere alla nostra app di chat dal vivo. Qui abbiamo la password dell'hash del negozio nel database, 
          quindi per convalidare la password dell'hash dobbiamo usare la funzione password_verify(). 
          Utilizzando questa funzione questo sistema può autenticare la password dell'utente. 
          Dopo il processo di autenticazione, dettagli utente particolari come ID utente e nome utente sono stati archiviati 
          nella variabile $ _SESSION e questo valore di variabile è possibile da tutto il sistema. 
          Dettagli di accesso dell'utente come il suo ID utente e i dettagli del timestamp sono stati inseriti 
          nella tabella login_details. Dopo aver inserito i dettagli di accesso nel database, 
          l'ultimo ID inserito della tabella login_details è stato ottenuto utilizzando il metodo lastInsertId() 
          e archiviato nella variabile $_SESSION['login_details_id']. 
          Questi dati aiuteranno a conoscere lo stato online di un particolare utente come se fosse online e offline. 

step2(index.php) --> Dopo l'accesso nell'applicazione di chat, l'utente verrà reindirizzato alla pagina dell'index. 
          Per accedere a questa parte è essenziale il login, senza averlo effettuato non vi si può accedere 
          Quindi, l'utente appena autenticatosi, può accedere solo a questa pagina. 
          Per questo qui abbiamo convalidato il valore della variabile $_SESSION['user_id']. 
          Qui vi si trova anche il link alla pagina di logout.

step3(logout.php) --> collegamento di logout. Dopo aver fatto clic su questo collegamento, 
          ci disconnetteremo da questo sistema e la pagina sarà stata reindirizzata alla pagina login.php. 
          Di seguito puoi trovare il codice della pagina logout.php.

step4(index.php) --> In questa pagina vogliamo visualizzare tutti i dati degli utenti disponibili nella tabella di login.
            Quindi l'utente di accesso può decidere a quale persona desidera scrivere. 
            In questo passaggio abbiamo un semplice recupero dei dati utente 
            dalla tabella di accesso e visualizzati nella pagina dell'index.

step5(fetch_user.php) --> tag con tag id="user_details", sotto questo tag visualizzerà il formato della tabella dei dettagli dell'utente. 
            Per i dettagli sul recupero, qui abbiamo la funzione make che invia la richiesta ajax alla pagina fetch_user.php. 
            Questo recupera i dati dell'utente e li converte in html 
            e li invia alla funzione ajax che è stata visualizzata sulla pagina web.

step6(index.php) --> Poiché questa è la parte principale in questo tramite questa finestra di dialogo, gli utenti possono chattare tra loro. 
            Per questo come possiamo creare una finestra di dialogo di chat dinamica per ciascuno. 
            Per questo abbiamo creato una funzione jquery su index.php. 
            Questa funzione genererà dinamicamente il codice html per la finestra di dialogo della chat. 
            Qui per la finestra di dialogo della chat abbiamo utilizzato il plug-in della finestra 
            di dialogo dell'interfaccia utente di JQuery. 
            Quindi, quando abbiamo chiamato questa funzione, questa funzione genererà codice html per la finestra di dialogo della chat. 
            Di seguito puoi trovare il codice sorgente per la generazione della finestra di dialogo della chat dinamica.

step7(index.php) --> Nel codice sorgente di cui sopra abbiamo scritto la pagina index.php. 
            Qui possiamo vedere la funzione make_chat_dialog_box(). 
            Questa funzione genererà una finestra di dialogo chat per ogni utente
            in base al valore dell'argomento to_user_id e to_user_name. 
            Quindi, in base al valore di entrambi gli argomenti, questa funzione creerà una finestra di dialogo di chat dinamica 
            per ogni utente. Ora, quando questa funzione verrà chiamata, questa funzione verrà chiamata
            quando faremo clic sul pulsante chat stat. Quindi qui possiamo vedere il codice jquery in cui possiamo vedere 
            la classe del pulsante di avvio della chat .start_chat che è il selettore con l'evento click. 
            Quindi, quando abbiamo fatto clic su questo pulsante, recupererà il valore dall'attributo data-touserid 
            e data-tousername e memorizzerà nella variabile. 
            Dopo questo ha chiamato la funzione make_chat_dialog_box(to_user_id, to_user_name) e creerà una finestra di dialogo 
            di chat dinamica per un particolare utente di cui abbiamo fatto clic sul pulsante di avvio della chat. 
            Quindi, in questo modo possiamo creare una finestra di dialogo di chat dinamica nella nostra applicazione di chat online 
            usando PHP.



 


