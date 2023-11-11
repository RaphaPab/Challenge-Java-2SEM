# Challenge-Java-2SEM

# Apresentação do projeto



# Endpoints

## Usuario
- [Login](#login)
- [Buscar usuário](#buscar_usuário)
- [Cadastrar usuário](#cadastrar_usuário)
- [Atualizar usuário](#atualizar_usuário)
- [Deletar usuário](#deletar_telefone)

## Telefone
- [Listar telefones por ID de usuário](#listar_telefone_por_id)
- [Cadastrar telefone](#cadastar_telefone_usuario)
- [Atualizar telefone](#atualizar_usuário)
- [Deletar telefone](#deletar_telefone)

## Email
- [ID do Email](#id_do_email)
- [Cadastrar email](#cadastar_email_usuario)
- [Atualizar email](#atualizar_usuário)
- [Deletar email](#deletar_email)


---
padrão

GET 
- endpoint
- exemplo corpo de resposta
- http responses

POST
- endpoint
- tabela de atributos para request
- exemplo corpo de request
- exemplo corpo de resposta 
- http responses

PUT
- endpoint
- tabela de atributos para request
- exemplo corpo de request
- exemplo corpo de resposta 
- http responses

DELETE
- endpoint 
- exemplo de request 
- não há corpo de resposta 
- http responses
---

## Usuário

### Login
(-------CORRIGIR---------)
`POST` /localhost:8080/api/login

|    Campo     | Tipo | Obrigatorio | Descrição
|--------------|------|:-----------:|---------------------------------------------|
|    Email     |String|     Sim     | Campo para que insira o email para acesso
|     CNH      | Int  |     Sim     | Código de autorização do usuário para acesso 



**Exemplo Corpo do request**(-----------EDUUUUU---------)
```JSON
{
    "email":"email@email.com",
    "CNH":"42897796822"
}
```

**Exemplo corpo de reposta**(-------------CORRIGIR----------)
```JSON
{ 
    "token": <token gerado>,
    "type": "JWT",
    "prefix": "Bearer"
}
```
**HTTP responses para POST**
| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success)|
| `400` | Bad request|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|

---
### Listar_Usuários

`GET` /localhost:8080/api/usuario (---------CORRIGIR---------)

**Exemplo Corpo de resposta**

```JSON
[
    {
        "id": 1,
        "nome": "nieke",
        "username": "nike",
        "senha": "nike"
    },
    {
        "id": 2,
        "nome": "nieke",
        "username": "nike",
        "senha": "nike"
    }
]
```
**HTTP responses para GET**
| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success)|
| `400` | Bad request|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---


### Buscar_Usuário (___________CORRIGIR__________)

`GET` /localhost:8080/api/usuario/{id}

**Exemplo Corpo de resposta**
```JSON
{
    "id": 1,
    "nome do cliente": "kaio",
    "data de nascimento": "1990-07-21",
    "numero cnh": "11111111111",
    "numero cpf": "11111111111",
    "numero rg": "1234567"",
    "data cadastro": "2022-07-25"

}
```
**HTTP responses para `GET`**
| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success)|
| `400` | Bad request|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
### Cadastrar_Usuário

`POST` /localhost:8080/api/usuario

**Atributos do request**
|        Campo         |   Tipo   | Obrigatorio |  Descrição
|----------------------|----------|:-----------:|--------------------------------------------------|
|  ID                  |   Int    |     Sim     | Campo para inserir o ID do cliente
|  Nome                |  String  |     Sim     | Campo para inserir nome do cliente
|  Data de Nasc        |Local_date|     Sim     | Campo para inserir data de nascimento do cliente
|  CNH                 |   Int    |     Sim     | Campo para inserir a CNH do cliente
|  CPF                 |   Int    |     Sim     | Campo para inserir o CPF do cliente
|  RG                  |   Int    |     Sim     | Campo para inserir o RG do cliente
|  Data de Cadastro    |Local_date|     Sim     | Campo para inserir a data de cadastro do cliente


**Exemplo Corpo do request** (-----------CORRIGIR__------------)
```JSON
{
    "nome": "Jose Augusto da Silva",
    "username": "JoseGuto",
    "senha": "222222"
}

```

**Exemplo corpo de resposta**
```JSON
{
    "id": 3,
    "nome": "CJose Augusto da Silvaarlos",
    "username": "JoseGuto",
    "senha": "222222@",
    "enabled": true,
    "accountNonExpired": true,
    "credentialsNonExpired": true,
    "authorities": [
        {
            "authority": "ROLE_USUARIO"
        }
    ],
    "password": "222222@",
    "accountNonLocked": true
}
```

**HTTP responses para POST**
| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success)|
| `400` | Bad request|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
### Atualizar_Usuário

`PUT` /localhost:8080/api/usuario/{id}


**Atributos do request**
|        Campo         |   Tipo   | Obrigatorio |  Descrição
|----------------------|----------|:-----------:|--------------------------------------------------|
|  ID                  |   Int    |     Sim     | Campo para inserir o ID do cliente
|  Nome                |  String  |     Sim     | Campo para inserir nome do cliente
|  Data de Nasc        |Local_date|     Sim     | Campo para inserir data de nascimento do cliente
|  CNH                 |   Int    |     Sim     | Campo para inserir a CNH do cliente
|  CPF                 |   Int    |     Sim     | Campo para inserir o CPF do cliente
|  RG                  |   Int    |     Sim     | Campo para inserir o RG do cliente
|  Data de Cadastro    |Local_date|     Sim     | Campo para inserir a data de cadastro do cliente

**Exemplo Corpo do request** (-----------CORRIGIR__------------)

```JSON
{
    "nome":"java",
    "username":"java",
    "senha": "java"
}
```

**Exemplo Corpo do response**
```JSON
{
    "id": 1,
    "nome": "java",
    "username": "java",
    "senha": "java"
}
```

**Respostas que podem aparecer no `PUT` :**
| Código | Descrição |
|---|---|
| `201` | criado com sucesso (success)|
| `400` | Bad request|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
### Deletar_Usuário

`Delete` /localhost:8080/api/usuario/{id}

Retorna um arquivo JSON vazio.

**Respostas que podem aparecer no DELETE :**

| Código | Descrição |
|---|---|
| `204` | Requisição executada com sucesso (success).|
| `400` | Erros de validação ou os campos informados não existem no sistema|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `405` | Método não implementado.|
| `500` | Internal server error|
---

## Telefone

### Listar_Telefone_por_ID (-----------CORRIGIR__------------)
`GET` /localhost:8080/api/telefone/


```JSON
{
    "id": 1,
    "telefone": "956783112",
    "ddd": "011",
    "ddi": "+55",
    "usuario":{
        "id": 1,
        "nome": "Maria",
        "username": "carlitos",
        "senha": "alo"
    }
}
```
**HTTP responses para `GET`**
| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success)|
| `400` | Bad request|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
------------------------------------------------------------------------------------------------------------------------
### Cadastar_Email_Cliente
`POST` /localhost:8080/api/email/

|    Campo         | Tipo   | Obrigatorio | Descrição
|------------------|--------|:-----------:|--------------------------------------------------------------|
| id do email      | Int    |     Sim     | Campo que contém o código do email do cliente
| dados do email   | String |     Sim     | Contém o código de endereçamento de email (email@email.com)
| status do email  | String |     Sim     | Contém o status do email do cliente(ativo ou inativo)

**Exemplo do Corpo do Request**(-----------CORRIGIR__------------)
```JSON
{
   EMAILLLLLLLL
    }
}
```
**Exemplo do Corpo do Response**(-----------CORRIGIR__------------)
```JSON
{
    EMaiiillllllllLLLLL
},
```
**Respostas que podem aparecer no POST :**
| Código | Descrição |
|---|---|
| `201` | criado com sucesso (success)|
| `400` | Bad request|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
### Atualizar_Email

`PUT` /localhost:8080/api/email/

|    Campo         | Tipo   | Obrigatorio | Descrição
|------------------|--------|:-----------:|--------------------------------------------------------------|
| id do email      | Int    |     Sim     | Campo que contém o código do email do cliente
| dados do email   | String |     Sim     | Contém o código de endereçamento de email (email@email.com)
| status do email  | String |     Sim     | Contém o status do email do cliente(ativo ou inativo)


**Exemplo do Corpo do Request**
```JSON
{
     EMAILLLLLLLL
}
```
**Exemplo do Corpo do Response**
```JSON
{
     EMAILLLLLLLL
        }
},
```
**Respostas que podem aparecer no PUT :**
| Código | Descrição |
|---|---|
| `204` | Requisição executada com sucesso (success)|
| `400` | Erros de validação ou os campos informados não existem no sistema|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `405` | Método não implementado.|
| `500` | Internal server error|
---
### Deletar_Email

`Delete` /localhost:8080/api/email/{id}

Retorna um arquivo JSON vazio.

**Respostas que podem aparecer no `DELETE` :**

| Código | Descrição |
|---|---|
| `204` | Requisição executada com sucesso (success).|
| `400` | Erros de validação ou os campos informados não existem no sistema|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `405` | Método não implementado.|
| `500` | Internal server error|
---


------------------------------------------------------------------------------------------------------------------------------------




### Cadastar_Telefone_Usuario
`POST` /localhost:8080/api/telefone/

|    Campo         | Tipo | Obrigatorio | Descrição
|------------------|--------|:-----------:|------------------------------------------------------|
| id do telefone   | Int    |     Sim     | Campo que contém o ID do cliente 
| telefone         | Int    |     Sim     | Campo que contém o telefone do usuário até 9 digitos 
| ddd              | String |     Sim     | Contém o código de endereçamento urbano brasileiro
| ddi              | String |     Sim     | Contém o codigo de discagem direta internacional
| nome da operadora| String |     Sim     | Contém o nome da operadora de telefonia

**Exemplo do Corpo do Request** (-----------CORRIGIR__------------)
```JSON
{
    "telefone":"123456",
    "ddd":"011",
    "ddi":"55555",
    "usuario": {
        "id": 1,
        "nome": "Maria",
        "username": "carlitos",
        "senha": "alo"
    }
}
```
**Exemplo do Corpo do Response**(-------------EDUUUUUUUU_____________)
```JSON
{
    "id": 1,
    "telefone": "111111111",
    "ddd": "123",
    "ddi": "55555",
    "usuario": {
        "id": 1,
        "nome": "Carlos",
        "username": "carlitos",
        "senha": "alo"
        }
},
```
**Respostas que podem aparecer no POST :**
| Código | Descrição |
|---|---|
| `201` | criado com sucesso (success)|
| `400` | Bad request|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `500` | Internal server error|
---
### Atualizar_Telefone

`PUT` /localhost:8080/api/telefone/{id_usuario}

|    Campo         | Tipo   | Obrigatorio | Descrição
|------------------|--------|:-----------:|------------------------------------------------------|
| telefone         | String |     Sim     | Campo que contém o telefone do usuário até 9 digitos 
| ddd              | String |     Sim     | Contém o código de endereçamento urbano brasileiro
| ddi              | String |     Sim     | Contém o codigo de discagem direta internacional
| nome da operadora| String |     Sim     | Contém o nome da operadora de telefonia

**Exemplo do Corpo do Request** (-------------EDUUUUUUUU_____________)
```JSON
{
    "telefone":"123456",
    "ddd":"011",
    "ddi":"55555",
}
```
**Exemplo do Corpo do Response**
```JSON
{
    "id": 1,
    "telefone": "111111111",
    "ddd": "123",
    "ddi": "55555",
    "usuario": {
        "id": 1,
        "nome": "Carlos",
        "username": "carlitos",
        "senha": "alo"
        }
},
```
**Respostas que podem aparecer no PUT :**
| Código | Descrição |
|---|---|
| `204` | Requisição executada com sucesso (success)|
| `400` | Erros de validação ou os campos informados não existem no sistema|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `405` | Método não implementado.|
| `500` | Internal server error|
---
### Deletar_Telefone

`Delete` /localhost:8080/api/telefone/{id}
/localhost:8080/api/telefone/

Retorna um arquivo JSON vazio.

**Respostas que podem aparecer no `DELETE` :**

| Código | Descrição |
|---|---|
| `204` | Requisição executada com sucesso (success).|
| `400` | Erros de validação ou os campos informados não existem no sistema|
| `401` | Dados de acesso inválidos|
| `404` | Registro pesquisado não encontrado (Not found)|
| `405` | Método não implementado.|
| `500` | Internal server error|
---


# Diagrama de Classes(-------------EDUUUUUUUU_____________)
![Diagrama de classes]
