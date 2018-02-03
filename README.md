# Modelo de documentação para API no Github

Ola galera, segue aqui um modelo para documentar uma API através do github caso vocês precisem.

Eu me inspirei/traduzi neste 
[gist](https://gist.github.com/iros/3426278#file-example-md) do [IROS](https://gist.github.com/iros).

## Nome da chamada API  
* Buscar usuario
* Autenticar usuario
* Buscar relatorio
## Informações adicionais sobre sua chamada de API.
Retorna um JSON com informações da busca 

    * URL: /users/:id
    * Metodo: GET
    * URL Parametros:
        id = [inteiro]
    * Parametros:
        id: "nome"
    * Resposta de sucesso(200): { id: 12, name: "Lucas de Oliveira" }
    * Resposta de erro(404): { error: "Não encontrado" }
    * Resposta de erro(401): { error: "Você não está autorizado a fazer esse pedido." }
    *Modelo da chamada: 
    ```javascript
        $.ajax({
            url: "/users/1",
            dataType: "json",
            type : "GET",
            success : function(r) {
                console.log(r);
            }
        });
    ```
<!--# URL

<The URL Structure (path only, no root url)>

Method:

<The request type>

GET | POST | DELETE | PUT

URL Params

<If URL params exist, specify them in accordance with name mentioned in URL section. Separate into optional and required. Document data constraints.>

Required:

id=[integer]

Optional:

photo_id=[alphanumeric]

Data Params

<If making a post request, what should the body payload look like? URL Params rules apply here too.>

Success Response:

<What should the status code be on success and is there any returned data? This is useful when people need to to know what their callbacks should expect!>

Code: 200 
Content: { id : 12 }
Error Response:

<Most endpoints will have many ways they can fail. From unauthorized access, to wrongful parameters etc. All of those should be liste d here. It might seem repetitive, but it helps prevent assumptions from being made where they should be.>

Code: 401 UNAUTHORIZED 
Content: { error : "Log in" }
OR

Code: 422 UNPROCESSABLE ENTRY 
Content: { error : "Email Invalid" }
Sample Call:

<Just a sample call to your endpoint in a runnable format ($.ajax call or a curl request) - this makes life easier and more predictable.>

Notes:

<This is where all uncertainties, commentary, discussion etc. can go. I recommend timestamping and identifying oneself when leaving comments here.>