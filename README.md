
# authenticathor-core-identity

API de autenticação baseada em JSON Web Tokens (JWT) usando ASP.NET Core Identity. Esta aplicação oferece recursos de autenticação, geração de tokens JWT e proteção de rotas usando autenticação de portador JWT.

## Configuração

1. **Instalação das Dependências:**
   Certifique-se de ter o .NET SDK instalado. Execute o seguinte comando para instalar as dependências:
   ```bash
   dotnet restore
   ```


2. **Configuração do Banco de Dados e Docker**:

Configure a string de conexão do banco de dados no arquivo appsettings.json:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "SuaStringDeConexao"
  },
  
}
```

Execute as migrações para criar o banco de dados:
```bash
dotnet ef database update

```

Use o Docker Compose para iniciar o SQL Server e a aplicação:
```bash

docker-compose up -d
```

## Uso/Exemplos

1. **Autenticação**:
Envie uma solicitação POST para /api/auth/login com um corpo JSON contendo as credenciais do usuário para obter um token JWT.

Exemplo de solicitação:
```json
   {
     "Username": "SeuUsuario",
     "Password": "SuaSenha"
   }
```

   
2. **Registro de Usuário**:
Envie uma solicitação POST para /api/auth/register com um corpo JSON contendo informações do usuário para registrar um novo usuário.

Exemplo de solicitação:

  ```json
  {
     "Username": "NovoUsuario",
     "Email": "novousuario@example.com",
     "Password": "SenhaSegura123"
   }
   ```
3. **Verificação do Token:**
Ao acessar rotas protegidas, inclua o token JWT no cabeçalho de autorização da solicitação HTTP. Por exemplo:

```http
curl -H "Authorization: Bearer SeuTokenJWT" https://sua-api.com/rota-protegida
```
Certifique-se de substituir SeuTokenJWT pelo token JWT recebido durante o processo de autenticação.

**Docker Compose**

Se você preferir usar Docker Compose, basta executar o seguinte comando para iniciar o SQL Server e a aplicação:

```bash

docker-compose up -d
```



## Stack utilizada

**Back-end:** C#, .Net 6


## Licença

[MIT](https://choosealicense.com/licenses/mit/)

