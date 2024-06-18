# Quando Lança API
- [Rota /users](#rotausers)
  - [Registrar um novo usuário](#registrarusuario)
  - [Fazer login](#fazerlogin)
- [Rota /wishlist](#rotawishlist)
  - [Recuperar Jogos Favoritados Pelo Usuário](#favoritos)
  - [Adicionar Jogo aos Favoritos](#adicionarfavoritos)
  - [Remover Jogo dos Favoritos](#removerfavoritos)
 

## Rota /users
<a name="#rotausers"></a>
## Registrar um novo usuário
<a name="#registrarusuario"></a>
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
<a name="#fazerlogin"></a>
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

## Rota /wishlist
## Recuperar Jogos Favoritados Pelo Usuário
<a name="#favoritos"></a>
- **Rota**: `/wishlist/`
- **Método**: `GET`
- **Descrição**: Retorna todos os jogos adicionados aos favoritos pelo usuário.
- **Corpo da Requisição**:
  </br></br>
    ```txt
        Authorization: {{Token de Usuário}}
    ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        [
        	{
        		"id": "e9c40a4a-2c6e-44a1-8ab8-05fdcec14316",
        		"name": "Into the Radius 2",
        		"release": "To Be Announced",
        		"developer": "CM Games",
        		"image": "https://assets-prd.ignimgs.com/2024/05/17/untitled-1-1715983716012.png?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"platforms": [
        			"PC"
        		]
        	}
        ]
    ```










  - [Adicionar Jogo aos Favoritos](#adicionarfavoritos)
  - [Remover Jogo dos Favoritos](#removerfavoritos)
