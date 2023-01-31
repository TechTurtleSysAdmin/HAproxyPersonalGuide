# Il modello transazionale

- HTTP è un protocollo a transazione significa che ogni richiesta/risposta costituisce una singola transazione indipendente tra il client e il server.
- viene stabilita una connessione TCP dal client al server, il client invia una richiesta attraverso la connessione, il server risponde e la connessione viene chiusa.
- Una nuova richiesta comporterà una nuova connessione.

![alt text](https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP.png)
```
 [CON1] [REQ1] ... [RESP1] [CLO1] [CON2] [REQ2] ... [RESP2] [CLO2] ...
 ```
 
 - Questa viene chiamata modalità "HTTP chiusa", perchè: 
   - Il client invia una richiesta attraverso una connessione.
   - Il server risponde alla richiesta e chiude la connessione.


- A causa della natura transazionale del protocollo, è stato possibile migliorarlo per evitare di chiudere una connessione tra due transazioni successive
  - In questa modalità tuttavia, è obbligatorio che il server indichi la lunghezza del contenuto in modo che il client non attenda indefinitamente
  - Generalmente questo metodo è migliore della modalità "HTTP-close", ma non sempre perchè i client limitano il loro valore di transazioni concorrenti ad un numero piccolo.
```
 [CON] [REQ1] ... [RESP1] [REQ2] ... [RESP2] [CLO] ...
 ```
  
- Abbiamo anche la pipeline mode, dove il client non riceve subito una risposta ad una richiesta fatta, ma viene fatta una raccolta di tutte le richieste lato client (utile quando devono essere caricate molte immagini che compongono una pagina) e poi viene data una risposta cumulativa lato server.
  - Questo può ovviamente avere un enorme vantaggio sulle prestazioni, in quanto la latenza della rete di rete viene eliminata tra le richieste successive. Molti agent HTTP non supportano non supportano correttamente il pipelining, poiché non esiste un modo per associare una risposta alla risposta alla richiesta corrispondente in HTTP. Per questo motivo, è obbligatorio che il server risponda nello stesso ordine esatto in cui sono state ricevute le richieste. 
```
[CON] [REQ1] [REQ2] ... [RESP1] [RESP2] [CLO] ...
 ```
 
 HAProxy supporta 4 modalità di connessione:
 
| Nome | Definizione |
| ------------- | ------------- |
| keep alive  | Tutte le richieste e le risposte vengono processate (default)  |
| Tunnel | solo la prima richiesta e la prima risposta vengono elaborate, tutto il resto viene inoltrato senza analisi (deprecato) |
| Server Close | la connessione rivolta al server viene chiusa dopo la risposta. |
| Close | la connessione viene chiusa attivamente dopo la fine della risposta. |
