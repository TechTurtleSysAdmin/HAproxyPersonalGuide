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
```
 [CON] [REQ1] ... [RESP1] [REQ2] ... [RESP2] [CLO] ...
 ```
