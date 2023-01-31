# HTTP request

| Numero linea | Contenuto |
| ------------- | ------------- |
| 1 | GET /serv/login.php?lang=en&profile=2 HTTP/1.1  |
| 2 | Host: www.mydomain.com |
| 3 | User-agent: my small browser |
| 4 | Accept: image/jpeg, image/gif |
| 5 | Accept: image/png |

## Request Line
La request line è Numero linea 1 ed è sempre composta da 3 campi:

| :) | :) |
| ------------- | ------------- |
| METHOD | GET |
| URI | /serv/login.php?lang=en&profile=2 |
| version tag | HTTP/1.1 |

Lo URI può avere due forme:

| 🔗 | 🔗 |
| ------------- | ------------- |
| relative URI | /serv/login.php?lang=en&profile=2 |
| absolute URI | http://192.168.0.12:8080/serv/login.php?lang=en&profile=2 |
 
