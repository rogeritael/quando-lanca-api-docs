# Quando Lança API
- [Rota /games](#rotagames)
  - [Recuperar Todos os Jogos do Banco de Dados](#todososjogos)
  - [Recuperar Jogo pelo ID ou NOME](#encontrarjogo)
- [Rota /users](#rotausers)
  - [Registrar um novo usuário](#registrarusuario)
  - [Fazer login](#fazerlogin)
- [Rota /wishlist](#rotawishlist)
  - [Recuperar Jogos Favoritados Pelo Usuário](#favoritos)
  - [Adicionar Jogo aos Favoritos](#adicionarfavoritos)
  - [Remover Jogo dos Favoritos](#removerfavoritos)


## Rota /games
<a name="#rotagames"></a>
## Recuperar Todos os Jogos do Banco de Dados
<a name="#todososjogos"></a>
- **Rota**: `/games`
- **Método**: `GET`
- **Descrição**: Retorna todos os jogos anunciados do banco de dados.
- **Corpo da Requisição (opcional)**:
</p>minified retona apenas name, release e lançamento dos jogos</p>
</p>page faz a paginação dos dados, retornando 10 jogos por página</p>

  ```json
      {
        "minified": true,
        "page": 1
      }
  ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        [
        	{
        		"id": "6662d74b-48ce-4c59-aa1e-726f16f1086b",
        		"name": "Omega 6 The Video Game",
        		"release": "To Be Announced",
        		"developer": "Happymeal",
        		"image": "https://assets-prd.ignimgs.com/2023/09/20/omega6-1695252158706.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"background": "https://assets-prd.ignimgs.com/2023/09/20/omega6-1695252158706.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"platforms": [
        			"PC",
        			"Nintendo Switch"
        		],
        		"lançamento": "To Be Announced"
        	},
        	{
        		"id": "e6b2eceb-b3a5-448f-a7b6-af1dfcc80c1e",
        		"name": "Star Stuff",
        		"release": "2024-06-07T03:00:00.000Z",
        		"developer": "Ánimo Games Studio",
        		"image": "https://assets-prd.ignimgs.com/2023/06/14/starstuff-1686771593202.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"background": "https://assets-prd.ignimgs.com/2023/06/14/starstuff-1686771593202.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"platforms": [
        			"PC"
        		],
        		"lançamento": "Lançado há 12 dias."
        	},
          ...
        ]
    ```

## Recuperar Jogo pelo ID ou NOME
<a name="#encontrarjogo"></a>
- **Rota**: `/games/:term` separado por traço no caso de pesquisa por nome, ex: resident-evil-5-remake
- **Método**: `GET`
- **Descrição**: Retorna jogo pelo Id ou pelo nome.
- **Exemplos**:
  ```json
        http://localhost:5000/games/0547c392-9a2b-4b99-8622-7548934274d3

        http://localhost:5000/games/age-of-empires-mobile
  ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        [
        	{
        		"id": "0547c392-9a2b-4b99-8622-7548934274d3",
        		"name": "Age of Empires Mobile",
        		"release": "To Be Announced",
        		"developer": "World's Edge",
        		"image": "https://assets-prd.ignimgs.com/2022/10/25/age-of-empires-mobile-button-1-1666724649769.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"background": "https://assets-prd.ignimgs.com/2022/10/25/age-of-empires-mobile-button-1-1666724649769.jpg?width=300&crop=1%3A1%2Csmart&auto=webp",
        		"platforms": [
        			"Android",
        			"iPhone"
        		]
        	}
        ]
    ```



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

## Adicionar Jogo aos Favoritos
<a name="#adicionarfavoritos"></a>
- **Rota**: `/wishlist/add`
- **Método**: `POST`
- **Descrição**: Adiciona um jogo à lista de favoritos do usuário.
- **Corpo da Requisição**:
  </br></br>
    ```json
        {
        	"gameId": "898c211e-3c03-4e7a-a881-74f0922fb57d"
        }
    ```
    ```txt
        Authorization: {{Token de Usuário}}
    ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        {
        	"message": "jogo adicionado à lista de desejos com sucesso"
        }
  ```

## Remover Jogo dos Favoritos
<a name="#removerfavoritos"></a>
- **Rota**: `/wishlist/remove`
- **Método**: `DELETE`
- **Descrição**: Remove um jogo da lista de favoritos do usuário.
- **Corpo da Requisição**:
  </br></br>
    ```json
        {
        	"gameId": "898c211e-3c03-4e7a-a881-74f0922fb57d"
        }
    ```
    ```txt
        Authorization: {{Token de Usuário}}
    ```
- **Exemplo de Resposta**:
  </br>
  **status**: `200`
  </br></br>
  ```json
        {
        	"message": "Jogo removido da wishlist"
        }
  ```
