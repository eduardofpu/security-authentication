## Security com token
```
Objetivo desse projeto

Contruir uma API que realiza authentication e authorization com spring security

```
## Requisitos
```
Java 1.8

docker: Para subir o banco com postgres
docker-compose up

docker: Para derrubar o banco
docker-compose down

```

# Recursos para testar a api
```
POST  http://localhost:8080/login
GET   http://localhost:8080/v1/protected/estudents?page=0
POST  http://localhost:8080/v1/admin/estudents/1
DELET http://localhost:8080/v1/admin/estudents/1

```
#### Insira usuário admin e user no banco
```
INSERT INTO public.usuario
(id, "admin", "name", "password", username)
VALUES(1, true, 'toyo','$2a$10$Umt8cyNWdtZHZ.U2gYSGA.E6cjw.kMN.Luj3A9VQTtWierkTEQcea','toyo');

USUARIO: USER
username: oda
password:devdojo

INSERT INTO public.usuario(id, "admin", "name", "password", username)
VALUES(2, false, 'oda','$2a$10$Umt8cyNWdtZHZ.U2gYSGA.E6cjw.kMN.Luj3A9VQTtWierkTEQcea','oda');

```

#### Logar user o postman
```
No Auth do postman escolha a opção Basic Auth
coloque  o Username e o Password

logar como admin para executar o recurso POST:

POST http://localhost:8080/v1/admin/estudents

{"name":"Adriano","email":"adri@gmail.com"}

```



#### Listar os estudents
```
No Auth do postman escolha a opção Basic Auth
coloque  o Username e o Password

logar como admin ou user para executar o recurso GET:

GET http://localhost:8080/v1/protected/estudents?page=1

{
    "content": [
        {
            "name": "Adriano",
            "email": "adri@gmail.com",
            "id": 1
        }
    ],
    "last": true,
    "totalElements": 1,
    "totalPages": 1,
    "sort": null,
    "first": false,
    "numberOfElements": 4,
    "size": 5,
    "number": 1
}

```

#### Deletar  estudents
```
No Auth do postman escolha a opção Basic Auth
coloque  o Username e o Password

logar como admin para executar o recurso DELETE:

DELETE http://localhost:8080/v1/admin/estudents/1

{"name":"Adriano","email":"adri@gmail.com"}

```
