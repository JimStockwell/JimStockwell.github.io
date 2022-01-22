Today I learned that in a Spring Boot REST server, it is pretty standard to think of the project in three layers.
The top layer is the web API, the middle layer (or service layer) is the business logic, and bottom layer is the persistence layer.

Types in the web API layer are responsible for mediating between HTTP requests and services.
Besides being essentially a pass through layer, it checks and sets header fields.
There is enough here that it warrants its own layer.

Types in the service layer are for business logic.
Those services that are expected to be found by automatic scanning so they can be autowired into other types
should by marked by the @Services annotation.
(They get picked up in scanning
because @Services is itself annotated with @Component.  @Services doesn't actually do anything more than @Component,
except to document the fact that the type is incidentally part of the service layer.)

Types in the persistence layer are for handling persisting of the business data.
