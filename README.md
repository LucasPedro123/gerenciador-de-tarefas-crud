# DIO - Trilha .NET - API e Entity Framework
www.dio.me

## Descrição do projeto
Sistema gerenciador de tarefas, a qual você poderá cadastrar uma lista de tarefas que permitirá organizar melhor a sua rotina. Para isso, foi utilizado Entity Framework, ASP.NET e SQL Server.

## Contexto
Esse sistema gerenciador de tarefas,
fornece uma lista de tarefas com CRUD, ou seja, ele permiti a você obter os registros, criar, salvar e deletar.
A aplicação foi feita como MVC (Model, View, Controller), com intuito de trazer uma exibição de API de maneira mais visual para o usuário.

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
         
   
    
 `2 - Tenha o SQL Server instalado e, se tiver, coloque-o em execução.`

 `3 - Instale o EF (Entity Framework) CLI:`

    dotnet tool install --global dotnet-ef
 
  `4 - Instale todas as dependêndias do projeto`
  
      dotnet restore
  
  `5 - Altere o arquivo appsettings.Development.json com o nome do seu Banco de Dados`
 

  ```json
    {
      "ConnectionStrings":{
        "ConexaoPadrao": "Server=localhost\\!COLOCQUE AQUI O NOMEDO SEU BANDO DE DADOS!; Initial Catalog=GerenciamentoDeTarefas; Integrated Security=True;"
      }
    }

  ```
  `6 - Faça um migrations`
 
    dotnet-ef migrations add AdicionandoTabelaTarefas

  `7 - Adicione o migrations ao seu SQL Server`

    dotnet-ef database update

  `7 - Rode o projeto`

    dotnet watch run
---

## Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request com melhorias, correções de bugs ou novos recursos.