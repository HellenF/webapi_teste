# webapi_teste - Passo a passo da criação de API usando Swagger

Quanto tempo levou?
R: Aproximadamente 47 minutos.

Primeiro :
Criação de um  novo projeto por linha de código no termial do vs code

dotnet new webapi -n webapi_teste

code

enderendereço URL para conferir: https://localhost:5001/WeatherForecast



Segundo:

Colocar pra executar a aplicação 

comando: dotnet run

Em seguida parar de executar 

comando: Ctrl+C

Para incluir o Swagger no projeto

comando: dotnet add package SwashBuckle.AspNetCore

Terceiro:

Dentro do Startup.cs

Incluir 
services.AddSwaggerGen ();


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
Salvar o arquivo e executar novamente
dotnet run 

Rota padrão swagger:  https://localhost:5001/swagger/index.html

Dica legal:

Para não digitar no URL o swagger existe o comando RoutePrefix

comando: c.RoutePrefix = “”;

Quando ele é colocado dentro do UseSwaggerUI

Então, na hora de escrever é só colocar: https://localhost:5001
pois o routePrex, é o prefixo da rota que você quer para o swagger aparecer..

Também é possivel usar o padrão docs
c.RoutePrefix = "docs";











