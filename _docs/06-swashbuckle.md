# Swashbuckle

What is Swashbuckle?

Swashbuckle is an open-source Swagger implementation used for generating Swagger documentation for .NET Core APIs using .NET reflection.
This is living documentation, always in sync with the latest code.

There are three main components to Swashbuckle:

    Swashbuckle.AspNetCore.Swagger: 
        This component is the Swagger object model and middleware to expose SwaggerDocument objects as JSON endpoints.

    Swashbuckle.AspNetCore.SwaggerGen: 
        This library is a Swagger generator that builds SwaggerDocument objects directly from your routes, controllers, and models. 
        It's typically combined with the Swagger endpoint middleware to automatically expose Swagger JSON.

    Swashbuckle.AspNetCore.SwaggerUI: 
        This package is an embedded version of the Swagger UI tool. 
        It interprets Swagger JSON to build a rich, customizable experience for describing the web API functionality. 
        It includes built-in test harnesses for the public methods.

    Swashbuckle CLI: 
        This is a .NET global tool that once installed enables the ability of generating OpenAPI specifications during build/publish.

## Enrich your OpenAPI documentation with XML comments and annotations

### XML Comments

/// <summary>
/// Returns a group of Employees matching the given first and last names.
/// </summary>
/// <remarks>
/// Here is a sample remarks placeholder.
/// </remarks>
/// <param name="firstName">The first name to search for</param>
/// <param name="lastName">The last name to search for</param>
/// <returns>A string status</returns>
[HttpGet]
[Route("byname/{firstName}/{lastName}")]
public ActionResult<string> GetByName(string firstName, string lastName)
{
    return "Found another University employee";
}

## Data annotations

[Produces("application/json")]

[Consumes("application/json")]

Identify the potential HTTP response codes that could be returned to the calling client. 
[ProducesResponseType(StatusCodes.Status404NotFound)]

Your API may produce a standard set of response codes, in that case you can use the following attribute to specify 200, 400, and 404 instead of specifying each individually (see: https://docs.microsoft.com/en-us/aspnet/core/web-api/advanced/conventions?view=aspnetcore-6.0)
[ApiConventionMethod(typeof(DefaultApiConventions))]


Emit an operationId to significantly improve the API consumption experience including documentation, code-generation and integration with other services. 
You can automatically generate the operationId by including the Name property in the HTTP verb filter
[HttpGet("{Height}/{Width}", Name="GetPrice"]