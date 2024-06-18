# Quando Lança API
- Rota /users
  - Registrar um novo usuário
  - Fazer login
 

## Rota /users
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
  **status**: `200`
  </br></br>
  ```json
        {
          "message": "Usuário cadastrado com sucesso"
        }
    ```
