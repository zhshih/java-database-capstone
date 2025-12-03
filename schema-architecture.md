# Section 1: Architecture Summary

This Spring Boot application follows a hybrid architecture that combines MVC for server-rendered views and REST for API-driven modules. Thymeleaf templates are used to render the Admin and Doctor dashboards, handling page generation on the server side. All other application features—such as patient interactions, appointment management, and authentication—communicate through REST controllers that return JSON responses.

The application integrates two separate data stores: MySQL for structured relational data (patients, doctors, appointments, admins) and MongoDB for unstructured or flexible records such as prescriptions. All controllers interact with a centralized service layer, which contains the core business logic and coordinates operations between modules. The service layer then delegates to either JPA repositories for MySQL entities or MongoDB repositories for document-based models. This layered structure ensures loose coupling, clear separation of concerns, and easier maintainability.

# Section 2: Numbered Flow of Data and Control

1. A user initiates an action on either a Thymeleaf-rendered page (Admin or Doctor dashboard) or through a REST API endpoint (patient, appointment, or prescription module).

2. The request is sent to the appropriate controller—MVC controllers handle view-based interactions while REST controllers handle API calls.

3. The controller forwards the request to the corresponding service class, which encapsulates the application’s business logic.

4. The service layer determines which data source is required and communicates with the appropriate repository (JPA for MySQL or Mongo repositories for MongoDB).

5. The repository interacts with the database, performing CRUD operations such as fetching, updating, or storing data.

6. The data retrieved from the repository is returned to the service layer, which processes it and converts it into the required format.

7. The service sends the final response back to the controller, which either renders a Thymeleaf view or returns a JSON response to the client.