# Swashbuckle

What is Swashbuckle?

Swashbuckle is an open-source Swagger implementation used for generating Swagger documentation for .NET Core APIs using .NET reflection.
This is living documentation, always in sync with the latest code.

There are three main components to Swashbuckle:

    Swashbuckle.AspNetCore.Swagger: 
        This component is the Swagger object model and middleware to expose SwaggerDocument objects as JSON endpoints.

    Swashbuckle.AspNetCore.SwaggerGen: 
        This library is a Swagger generator that builds SwaggerDocument objects directly from your routes, controllers, and models. It's typically combined with the Swagger endpoint middleware to automatically expose Swagger JSON.

    Swashbuckle.AspNetCore.SwaggerUI: 
        This package is an embedded version of the Swagger UI tool. It interprets Swagger JSON to build a rich, customizable experience for describing the web API functionality. It includes built-in test harnesses for the public methods.

    Swashbuckle CLI: 
        This is a .NET global tool that once installed enables the ability of generating OpenAPI specifications during build/publish.
