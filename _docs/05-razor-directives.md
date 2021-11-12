# Razor directives

Razor directives are component markup used to add C# inline with HTML. With directives, developers can define single statements, methods, or larger code blocks.


You can use @expression() to add a C# statement inline with HTML. 

If you require more code, use the @code directive to add multiple statements enclosed by parentheses.

You can also add an @functions section to the template for methods and properties. 
They're added to the top of the generated class, where the document can reference them.

The @Page directive is special markup that identifies a component as a page.
Use this directive to specify a route. 
The route maps to an attribute route that the Blazor engine recognizes to register and access the page.

Use @bind markup to bind a C# variable to an HTML object. You define the C# variable by name as a string in the HTML.