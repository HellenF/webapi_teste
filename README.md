# webapi_teste - Passo a passo da criação de API usando Swagger

Quanto tempo levou?

R: Aproximadamente 47 minutos.

:heavy_check_mark: Primeiro :
Criação de um  novo projeto por linha de código no termial do vs code

dotnet new webapi -n webapi_teste

code

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92614303-47aeb380-f292-11ea-8543-fc600194d5ec.png)

enderendereço URL para conferir: https://localhost:5001/WeatherForecast



:heavy_check_mark: Segundo:

Colocar pra executar a aplicação 

comando: dotnet run

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
Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613081-ec2ff600-f290-11ea-9fdb-adadfb2e46fe.png)

Salvar o arquivo e executar novamente
dotnet run 

Rota padrão swagger:  https://localhost:5001/swagger/index.html

Resultado: 

![image](https://user-images.githubusercontent.com/28712925/92613247-226d7580-f291-11ea-945d-91ad815b264d.png)

:heavy_check_mark:Dica legal:

Para não digitar no URL o swagger existe o comando RoutePrefix

comando: c.RoutePrefix = “”;

Quando ele é colocado dentro do UseSwaggerUI

Então, na hora de escrever é só colocar: https://localhost:5001
pois o routePrex, é o prefixo da rota que você quer para o swagger aparecer..

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613417-56e13180-f291-11ea-9539-c87324f878ea.png)


Também é possivel usar o padrão docs
c.RoutePrefix = "docs";

Resultado:

![image](https://user-images.githubusercontent.com/28712925/92613466-65c7e400-f291-11ea-88bf-3ea27f8cbb65.png)











