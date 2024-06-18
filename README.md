# Quando Lança API
- [Rota /users](#rotausers)
  - [Registrar um novo usuário](#registrarusuario)
  - [Fazer login](#fazerlogin)
 

## Rota /users
<a name="#rotausers"></a>
## Registrar um novo usuário
- **Rota**: `/users/register`
- **Método**: `POST`
- **Descrição**: Cadastra um novo usuário.
- **Corpo da Requisição**:
  </br></br>
    ```json
        {
            "username": "mariaborba",
            "email": "mariah@hotmail.com",
            "password": "123456",
        }
    ```
- **Exemplo de Resposta**:
  </br>
  **status**: `201`
  </br></br>
  ```json
        {
          "message": "Usuário cadastrado com sucesso"
        }
    ```

</br></br>
## Fazer Login
- **Rota**: `/users/login`
- **Método**: `POST`
- **Descrição**: Faz login e retorna o token do usuário.
- **Corpo da Requisição**:
  </br></br>
    ```json
        {
            "username": "@mariaborba", //username com @ na frente
            "password": "123456",
        }
    ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        {
        	"message": "login realizado com sucesso",
        	"token": "eyJhbGciOiJIUzI1NiIsdgrInR5cCI6IkpXVCJ9.eyJpZCIZiYzk4MzRlL4h68jItNDUzMy1hZThjLTgxYmE1MjU0ZDc1YiIsImlhdCI6MTcxODY4MjgxNH0.vlOyNwfTr6hMBqA6Dru3P6s3_85GjkiaiIw7RMLAuNg"
        }
    ```
