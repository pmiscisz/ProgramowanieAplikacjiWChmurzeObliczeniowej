## 1. Utworzenie sieci
```bash
docker network create lab11
```

## 2. Uruchomienie kontenerów
### Kontener web1:

```bash
docker run -d --name web1 --network lab11 -p 8081:80 `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\html\web1:/usr/share/nginx/html" `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\logs\web1:/var/log/nginx" `
  nginx:latest
```
### Kontener web2:
```bash
docker run -d --name web2 --network lab11 -p 8082:80 `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\html\web2:/usr/share/nginx/html" `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\logs\web2:/var/log/nginx" `
  nginx:latest
```

### Kontener web3:
```bash
docker run -d --name web3 --network lab11 -p 8083:80 `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\html\web3:/usr/share/nginx/html" `
  -v "C:\Users\Patryk\Documents\Github\ProgramowanieAplikacjiWChmurzeObliczeniowej\lab11\logs\web3:/var/log/nginx" `
  nginx:latest
```

## 3. Weryfikacja
### Sprawdzenie sieci:
```bash
docker network ls
```
### Wynik:
```bash
NETWORK ID     NAME                      DRIVER    SCOPE
afbe96ba8f18   bridge                    bridge    local
b6521dbd7f0e   host                      host      local
6130b99c84e3   lab7_dockertest_default   bridge    local
6a72aab94571   lab11                     bridge    local
```
### Sprawdzenie działania kontenerów:
```bash
docker ps
```
### Wynik:
```bash
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                  NAMES
a69fc62eae9c   nginx:latest   "/docker-entrypoint.…"   13 minutes ago   Up 13 minutes   0.0.0.0:8083->80/tcp   web3
d3ea6c36572c   nginx:latest   "/docker-entrypoint.…"   13 minutes ago   Up 13 minutes   0.0.0.0:8082->80/tcp   web2
1f4695397b67   nginx:latest   "/docker-entrypoint.…"   13 minutes ago   Up 13 minutes   0.0.0.0:8081->80/tcp   web1
```
### Test curl (web1)
```bash
curl http://localhost:8081
```
### Wynik:
```bash
StatusCode        : 200
StatusDescription : OK
Content           : <!DOCTYPE html>
                    <html>

                    <body>
                        <h1>Lab 11 - Patryk Miscisz - WEB1</h1>
                    </body>

                    </html>
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    Accept-Ranges: bytes
                    Content-Length: 98
                    Content-Type: text/html
                    Date: Mon, 02 Jun 2025 17:37:06 GMT
                    ETag: "683dde67-62"
                    Last-Modified: Mon, 02 Jun 2025 17...
Forms             : {}
Headers           : {[Connection, keep-alive], [Accept-Ranges, bytes], [Content-Length, 98], [Content-Type, text/html]...}
Images            : {}
InputFields       : {}
Links             : {}
ParsedHtml        : mshtml.HTMLDocumentClass
RawContentLength  : 98
```