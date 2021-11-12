# API Attributes

[ApiController] enables opinionated behaviors that make it easier to build web APIs. Some behaviors include parameter source inference, attribute routing as a requirement, and model validation error handling enhancements.

When a controller is annotated with the [ApiController] attribute, it's implied that the any REST parameters will be found in the request body.
(Example of opinionated behaviours)

[Route] defines the routing pattern [controller]. The [controller] token is replaced by the controller's name (case-insensitive, without the Controller suffix). Requests to https://localhost:{PORT}/weatherforecast are handled by this controller.

The route may contain static strings, as in 'api/[controller]'. 
In this example, a request to https://localhost:{PORT}/api/weatherforecast would be handled by this controller.

