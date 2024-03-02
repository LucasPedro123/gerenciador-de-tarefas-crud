# ASP.NET - API e Entity Framework

## Descrição do projeto
Sistema gerenciador de tarefas, a qual você poderá cadastrar uma lista de tarefas que permitirá organizar melhor a sua rotina. Para isso, foi utilizado Entity Framework, ASP.NET e SQL Server.

## Contexto
O sistema disponibiliza uma API com endpoints para gerenciamento das tarefas. Utiliza o padrão MVC (Model, View, Controller) para fornecer uma interface visual amigável.

A sua classe principal, ou a Entidade, contém as seguintes propriedades:

![Diagrama da classe Tarefa](/Imgs/diagrama.png)


## Métodos de se chamar a API:


**Swagger**


![Métodos Swagger](/Imgs/swagger.png)


**Endpoints**


| Verbo  | Endpoint                | Parâmetro | Body          |
|--------|-------------------------|-----------|---------------|
| GET    | /Tarefa/{id}            | id        | N/A           |
| PUT    | /Tarefa/{id}            | id        | Schema Tarefa |
| DELETE | /Tarefa/{id}            | id        | N/A           |
| GET    | /Tarefa/ObterTodos      | N/A       | N/A           |
| GET    | /Tarefa/ObterPorTitulo  | titulo    | N/A           |
| GET    | /Tarefa/ObterPorData    | data      | N/A           |
| GET    | /Tarefa/ObterPorStatus  | status    | N/A           |
| POST   | /Tarefa                 | N/A       | Schema Tarefa |

Esse é o schema (model) de Tarefa, utilizado para passar para os métodos que exigirem

```json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2022-06-08T01:31:07.056Z",
  "status": "Pendente"
}
```

## Como rodar o projeto
 
`1 - Clone o repositório`

    git clone https://github.com/LucasPedro123/gerenciador-de-tarefas-crud
         
   
    
 `2 - Certifique-se de que o SQL Server está instalado e em execução.`



 `3 - Instale o Entity Framework CLI:`

    dotnet tool install --global dotnet-ef
 
  `4 - Instale as dependências do projeto:`
  
      dotnet restore
  
  `5 - Edite o arquivo appsettings.Development.json com as informações do seu Banco de Dados:`
 
  ```json
    {
      "ConnectionStrings":{
        "ConexaoPadrao": "Server=localhost\\!COLOCQUE AQUI O NOMEDO SEU BANDO DE DADOS!; Initial Catalog=GerenciamentoDeTarefas; Integrated Security=True;"
      }
    }

  ```

  `6 - Execute a migração:`
 
    dotnet-ef migrations add AdicionandoTabelaTarefas

  `7 - Aplique a migração ao seu SQL Server`

    dotnet-ef database update

  `7 - Rode o projeto`

    dotnet watch run
---

## Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request com melhorias, correções de bugs ou novos recursos.
