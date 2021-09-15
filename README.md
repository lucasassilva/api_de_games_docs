## API de Games
Esta API é utilizada principalmente para listar, criar, atualizar e deletar games.


## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games.
#### Parametros
Nenhum.
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta: 
```
[
    {
        "id": 1,
        "title": "Call of duty MW",
        "year": 2019,
        "price": 60
    },
    {
        "id": 2,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 3,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.

Motivos: Token inválido, Token expirado

Exemplo de resposta: 
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por realizar o processo de login
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "rodrigo232@gmail.com",
    "password": "123456"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta: 
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJyb2RyaWdvMjMyQGdtYWlsLmNvbSIsImlhdCI6MTYzMTcyNjM0NywiZXhwIjoxNjMxODk5MTQ3fQ.WQgv70SSQ_0KAacC1Jj9d0j0g8HpIHK5k1sTmOLw-wU"
}
```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.

Motivos: Senha ou e-mail incorretos.

Exemplo de resposta: 
```
{
    err: "Credenciais inválidas!"
}
```

