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