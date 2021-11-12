# dotnet CLI

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\RazorPagesPizza (main)
PS> dotnet new webapp

dotnet new page --name Pizza --namespace RazorPagesPizza.Pages --output Pages

----------------

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\ContosoPizza (main)
PS> dotnet new webapi
The template "ASP.NET Core Web API" was created successfully

.NET HTTP Read-Eval-Print Loop (REPL) command-line tool (for making HTTP requests to our web API)
(Currently this tool seems to be available only for .NET 5?)

dotnet tool install -g Microsoft.dotnet-httprepl

Usage:
httprepl https://localhost:{PORT}

------------------

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\BlazorApp (main)
PS> dotnet new blazorserver
The template "Blazor Server App" was created successfully

dotnet new razorcomponent -n Todo -o Pages

Razor component file names require a capitalized first letter. 
Open the Pages folder and confirm that the Todo component file name starts with a capital letter T. 
The file name should be Todo.razor.

----------------

PrintFramerAPI
http://localhost:5000/api/priceframe/6/17

dotnet add package Swashbuckle.AspNetCore

http://localhost:5000/swagger/v1/swagger.json
