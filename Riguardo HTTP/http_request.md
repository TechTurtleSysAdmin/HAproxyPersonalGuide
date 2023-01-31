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

| 🩹 | 🩹 |
| ------------- | ------------- |
| METHOD | GET |
| URI | /serv/login.php?lang=en&profile=2 |
| version tag | HTTP/1.1 |

Lo URI può avere due forme:

| 🔗 | 🔗 |
| ------------- | ------------- |
| relative URI | /serv/login.php?lang=en&profile=2 |
| absolute URI | http://192.168.0.12:8080/serv/login.php?lang=en&profile=2 |
 

# HTTP response

| Numero linea | Contenuto |
| ------------- | ------------- |
| 1 | HTTP/1.1 200 OK  |
| 2 | Content-length: 350 |
| 3 | Content-Type: text/html |


## Response Line
La response line è Numero linea 1 ed è sempre composta da 3 campi:

| 🩹 | 🩹 |
| ------------- | ------------- |
| version tag | HTTP/1.1 |
| status code | 200 |
| reason | OK |

Il codice dello stato è sempre di tre numeri. il primo numero indica uno stato generale :

| 🩹 | 🩹 |
| ------------- | ------------- |
| 1xx  | informational message to be skipped (e.g. 100, 101) |
| 2xx  | OK, content is following |
| 3xx  | OK, no content following |
| 4xx  | error caused by the client |
| 5xx  | error caused by the server |



| Code | When / reason |
| ------------- | ------------- |
| 200  | access to stats page, and when replying to monitoring requests |
| 301 | when performing a redirection, depending on the configured code |
| 302 | when performing a redirection, depending on the configured code |
| 303 | when performing a redirection, depending on the configured code |
| 307 | when performing a redirection, depending on the configured code |
| 308 | when performing a redirection, depending on the configured code |
|   |  |
|   |  |
|   |  |
|   |  |
|   |  |
|   |  |
|   |  |
|   |  |
|   |  |
