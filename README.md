# webapi_teste - Passo a passo da criação de API usando Swagger

Quanto tempo levou?

R: Aproximadamente 47 minutos.

:heavy_check_mark: Primeiro :

Criação de um  novo projeto por linha de código no termial do VS Code

dotnet new webapi -n webapi_teste

*webapi_teste é  nome escolhido

*dotnet new webapi -n é o comando para criar


code

é um comando pra abrir.
Basta clicar em Open Folder e encontrar o projeto.

![image](https://user-images.githubusercontent.com/28712925/92627552-e5f64580-f2a1-11ea-98b7-fa916c90c7c3.png)

Resultado:


![image](https://user-images.githubusercontent.com/28712925/92614303-47aeb380-f292-11ea-8543-fc600194d5ec.png)

Salvar ( Ctrl + S) e digitar no terminal

dotnet run

enderendereço URL para conferir: https://localhost:5001/WeatherForecast

![image](https://user-images.githubusercontent.com/28712925/92628735-aa5c7b00-f2a3-11ea-8099-6c261f1d1c99.png)

:heavy_check_mark: Segundo:

Em seguida parar de executar 

comando: Ctrl+C


Para incluir o Swagger no projeto

comando: dotnet add package SwashBuckle.AspNetCore

:heavy_check_mark:Terceiro:

Dentro do Startup.cs

Incluir 
services.AddSwaggerGen ();

Ficará assim:

![image](https://user-images.githubusercontent.com/28712925/92612270-18974280-f290-11ea-8384-108c1fdd2e0c.png)

app.UseSwagger (c => {

                c.SerializeAsV2 = true;
                
            });
            
            app.UseSwaggerUI (c => {
            
                c.SwaggerEndpoint (“/swagger/v1/swagger.json”, “My API V1");
                
            });
            
            if (env.IsDevelopment ()) {
            
                app.UseDeveloperExceptionPage ();
                
            }
            
-----------------------------------------------------------------------  
* Caso aconteça de aparecer erros - apagar e escever novamente as aspas (“/swagger/v1/swagger.json”, “My API V1");

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613081-ec2ff600-f290-11ea-9fdb-adadfb2e46fe.png)

Salvar o arquivo e executar novamente

dotnet run 



Resultado: 

![image](https://user-images.githubusercontent.com/28712925/92613247-226d7580-f291-11ea-945d-91ad815b264d.png)

Rota padrão swagger:  https://localhost:5001/swagger/index.html

![image](https://user-images.githubusercontent.com/28712925/92629671-0c69b000-f2a5-11ea-898c-8d59e5c14ed8.png)

:heavy_check_mark:Dica legal:

Para não digitar o swagger na URL existe o comando RoutePrefix

comando: c.RoutePrefix = “”;

* se aparecer erros é só apagar e escrever as aspas.

![image](https://user-images.githubusercontent.com/28712925/92630286-00322280-f2a6-11ea-9884-a639399983c6.png)

Quando ele é colocado dentro do UseSwaggerUI

Então, na hora de escrever é só colocar: https://localhost:5001
pois o routePrex, é o prefixo da rota que você quer para o swagger aparecer..

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613417-56e13180-f291-11ea-9539-c87324f878ea.png)


Também é possivel usar o padrão docs
c.RoutePrefix = "docs";

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613466-65c7e400-f291-11ea-88bf-3ea27f8cbb65.png)











